# AppFlowy with Supabase

AppFlowy is renowned for its user-friendly local app features. Recognizing the numerous requests for a cloud version, we're thrilled to announce that AppFlowy is now cloud-enabled! We've partnered with Supabase, an open-source alternative to Firebase, to handle user sign-ins and data storage. With a Supabase project, transforming AppFlowy into a self-hosted cloud app is straightforward. By the end of this article, you'll be primed to launch your very own AppFlowy cloud application with ease.

Let's explore how AppFlowy uses Supabase to implement the cloud features.

# Table of Contents

- [Authentication](#authentication)
  - [Dive in the code](#dive-in-the-code)
  - [Voila!](#voila)
- [Data storage](#data-storage)
  - [Architectural Design](#architectural-design)
  - [Supabase implementation](#supabase-implementation)
    - [Database schema](#database-schema)
    - [Dive in the code](#dive-in-the-code-1)
- [Realtime](#realtime)
  - [Dive in the code](#dive-in-the-code-2)


## Authentication

Initially, we considered building our own authentication service from scratch, one that would support social third-party authentication, magic links, and traditional email & password login. However, we soon realized that there were open-source projects available that already offer these features. That led us to the discovery of the Supabase authentication service, which provides multiple methods for user authentication.

- Email & password
- Magic links
- Social providers
- Phone logins

This is exactly what we need. We can leverage Supabase's authentication service to implement AppFlowy's authentication system. After follow the instructions in [this documentation](https://supabase.com/docs/guides/auth), we successfully set up the authentication service. 

### Dive in the code
Additionally, there's a Flutter package named [supabase_flutter](https://pub.dev/packages/supabase_flutter) which can be seamlessly integrated into AppFlowy. It perfectly meets our requirements. We utilize the `env` file to inject the supabase configuration into the app. Consequently, simply adding `supabase_flutter` and `envied` to the `pubspec.yaml` is all that's needed to kickstart the process.

```yaml
dependencies:
  supabase_flutter: ^1.10.4
  envied: ^0.3.0+3
  
dev_dependencies:
  envied_generator: ^0.3.0+3
```

**Configuring the .env File**

Start by creating a file named `.env` in the `appflowy_flutter` directory. Then, create the `env.dart` file, which defines the global environment variables.

* .env
```dotenv
SUPABASE_URL=https://xxx.supabase.co
SUPABASE_ANON_KEY=xxx
SUPABASE_JWT_SECRET=xxx
```

* env.dart

```dart
@Envied(path: '.env')
abstract class Env {
  @EnviedField(
    obfuscate: true,
    varName: 'SUPABASE_URL',
    defaultValue: '',
  )
  static final String supabaseUrl = _Env.supabaseUrl;
  @EnviedField(
    obfuscate: true,
    varName: 'SUPABASE_ANON_KEY',
    defaultValue: '',
  )
  static final String supabaseAnonKey = _Env.supabaseAnonKey;

  @EnviedField(
    obfuscate: true,
    varName: 'SUPABASE_JWT_SECRET',
    defaultValue: '',
  )
  static final String supabaseJwtSecret = _Env.supabaseJwtSecret;
}
```

Afterwards, run the following command to generate the `env.g.dart` file. This file contains the environment variables we defined in the `.env` file.

```shell
dart run build_runner build --delete-conflicting-outputs
```

**Initialize the supabase**

Before utilizing the Supabase instance, it must be initialized. This initialization takes place in the `supabase_task.dart` file. We define the 
`SupabaseLocalStorage` to customize the storage of the Supabase auth data.

```dart
 await Supabase.initialize(
   url: Env.supabaseUrl,
   anonKey: Env.supabaseAnonKey,
   debug: kDebugMode,
   localStorage: const SupabaseLocalStorage(),
 );
```

**Perform authentication**

Our authentication logic provided an abstract class named `AuthService`. This class's Supabase implementation can be found in `SupabaseAuthService`, specifically within the `supabase_auth_service.dart` file. 

```dart
 @override
  Future<Either<FlowyError, UserProfilePB>> signUpWithOAuth({
    required String platform,
    AuthTypePB authType = AuthTypePB.Supabase,
    Map<String, String> params = const {},
  }) async {
    final provider = platform.toProvider();
    final completer = supabaseLoginCompleter(
      onSuccess: (userId, userEmail) async {
        return await _setupAuth(
          map: {
            AuthServiceMapKeys.uuid: userId,
            AuthServiceMapKeys.email: userEmail,
            AuthServiceMapKeys.deviceId: await getDeviceId()
          },
        );
      },
    );

    final response = await _auth.signInWithOAuth(
      provider,
      queryParams: queryParamsForProvider(provider),
      redirectTo: supabaseLoginCallback,
    );
    if (!response) {
      completer.complete(left(AuthError.supabaseSignInWithOauthError));
    }
    return completer.future;
  }
```
The authentication flow is shown below:
1. The user clicks the login button in AppFlowy.
2. AppFlowy requests Supabase to start the authentication process.
3. Supabase prompts a web browser to open for authentication.
4. The user enters their credentials in the browser.
5. Once entered, the credentials are sent to Supabase for verification.
6. Supabase verifies the credentials and sends a user token back to AppFlowy.
7. AppFlowy updates to show the user they're logged in.


![](./uml-Authentication_Flow.png)

### Voila!
Ultimately, by clicking the Google login button, users are directed to a web browser to finalize the authentication process. Once authenticated, they are seamlessly redirected back to AppFlowy. Truly, integrating Supabase authentication into AppFlowy is a straightforward endeavor.

![login.png](login_image.png)

## Data storage

### Architectural Design

One of the prerequisites for AppFlowy Data Storage is the support for multiple cloud services. To achieve this, we've designed an abstraction layer that facilitates the integration of various cloud services. Each implementation provides the specific logic for the functions outlined in the AppFlowyServer interface. The architectural design is illustrated below:

![](./uml-AppFlowy_Server_Component_Diagram.png)

From the `AppFlowyServer` interface, it's evident that we can easily transition between various cloud services. For instance, moving from [Supabase](https://supabase.com/) to [Firebase](https://firebase.google.com/) or [Appwrite](https://appwrite.io/) is merely a matter of changing the implementation of the `AppFlowyServer` interface. The `AppFlowyServer` encompasses five services, with each service catering to a unique set of functionalities. Additionally, each service defines its own interface. Let's explore each of these components in detail.


* UserCloudService

The UserCloudService represents a standardized set of functionalities for interacting with a cloud-based user management service. This includes operations for registering new users, authenticating existing ones, managing user profiles, and handling user workspaces. In addition to basic user management, the interface provides methods for managing collaborative objects, subscribing to user updates, and receiving real-time events.

* DocumentCloudService

The `DocumentCloudService` represents a set of standardized functionalities for managing and retrieving information related to documents in a cloud service. It facilitates fetching updates to a given document, obtaining snapshots of a document up to a specified limit, and accessing the primary data of a document. This interface is designed to offer asynchronous operations to ensure efficient and non-blocking interactions when dealing with document data in a cloud environment.

* DatabaseCloudService

The `DatabaseCloudService` represents a set of standardized operations focused on collaborative objects within a cloud-based database. This interface allows for the retrieval of updates for a specific collaborative object, batch fetching of updates for multiple collaborative objects of a given type, and obtaining a set number of snapshots for a collaborative object. These functionalities ensure efficient and streamlined interactions when managing and accessing collaborative data in a cloud database environment.

* RemoteCollabStorage

The `RemoteCollabStorage` interface provides a suite of operations for managing collaborative objects in a remote storage system. This includes checking whether the remote storage is active and functions for retrieving all updates, snapshots, and the state of a collaborative object. Furthermore, there are methods to create snapshots and dispatch updates or initial states to the remote storage. The service is built with asynchronous operations in mind, as evident by the `async` keyword, ensuring that activities like fetching or sending data don't block other operations. It also allows subscribing to remote updates, giving users the capability to stay updated with changes in the collaborative object.


* FolderCloudService

The `FolderCloudService` interface outlines a set of operations centered around managing workspaces and folders in a cloud environment. It offers capabilities to create a new workspace and fetch data, snapshots, and updates related to a specific folder within a workspace. .

Currently, we only support Supabase as a cloud service provider. However, we intend to support other cloud services in the future. Let's explore how to implement the `AppFlowyServer` using Supabase.

### Supabase implementation
Upon integrating Supabase authentication, we discovered it inherently offers a PostgreSQL database. This advantage implies that individual users self-hosting AppFlowy on Supabase won't require separate data storage setups. Each Supabase project is pre-equipped with a dedicated PostgreSQL database, which we leverage to store AppFlowy's data.

### Database schema

We utilize the Postgres database to store:
1. User profiles
2. User settings
3. Data related to documents and databases generated within AppFlowy
4. Relationships between users and their associated workspaces

Here's what our schema looks like:

![schema.png](schema.png)

Let's introduce some of the tables and views in the schema:

1. **`af_roles` table**: Captures roles, e.g., 'Owner', 'Member', 'Guest'.

2. **`af_permissions` table**: Chronicles permissions, each featuring a name, description, and access tier.

3. **`af_role_permissions` table**: A junction table representing permissions assigned to roles.

4. **`af_user` table**: Houses user details, including a unique identifier (uid).

5. **`af_workspace` table**: Lists workspaces, each linked to a user via the user's uid.

6. **`af_workspace_member` table**: Associates members with their workspaces and respective roles.

7. **`af_collab` & `af_collab_member` tables**: Denote collaborations and their constituent members.

8. **Update tables**: (`af_collab_update`, `af_collab_update_document`, etc.): Handle collaboration updates.

9. **Statistics & snapshot tables**: (`af_collab_statistics`, `af_collab_snapshot`, `af_collab_state`): Track collaboration metrics and snapshots.

10. **`af_user_profile_view` view**: Fetches the latest workspace_id for every user.

We've developed a [tool](https://github.com/AppFlowy-IO/AppFlowy-Supabase) designed to set up the database tables, triggers, and functions within a Supabase PostgreSQL database. With this tool, a single command can configure your database. For a detailed guide, please consult [this documentation](https://github.com/AppFlowy-IO/AppFlowy-Supabase/tree/main/postgres).

### Dive in the code

AppFlowy's backend is developed in Rust, which requires a Rust crate to interact seamlessly with the Postgres database. Thankfully, the community has provided [postgrest-rs](https://github.com/supabase-community/postgrest-rs), a crate specifically designed to handle Supabase's Postgres database features. We've defined a struct named [SupabaseServer](https://github.com/AppFlowy-IO/AppFlowy/blob/main/frontend/rust-lib/flowy-server/src/supabase/server.rs) that implements the `AppFlowyServer` trait.

When interacting with the Postgres database, primarily CRUD operations are carried out. However, it's important to emphasize the value of the RPC function for customizing database actions. We've defined a function called `flush_collab_updates_v3`. This function locks the row with a specified OID, aggregates the updates into a single update, and then deletes the consolidated updates.

Here is the definition of the `flush_collab_updates_v3` function:
```plpgsql
CREATE OR REPLACE FUNCTION public.flush_collab_updates_v3(
        oid TEXT,
        new_value BYTEA,
        encrypt INTEGER,
        md5 TEXT,
        value_size INTEGER,
        partition_key INTEGER,
        uid BIGINT,
        workspace_id UUID,
        removed_keys BIGINT [],
        did TEXT
    ) RETURNS void AS $$
DECLARE lock_key INTEGER;
BEGIN -- Hashing the oid to an integer for the advisory lock
lock_key := (hashtext(oid)::bigint)::integer;
-- Getting a session level lock
PERFORM pg_advisory_lock(lock_key);
-- Deleting rows with keys in removed_keys
DELETE FROM af_collab_update
WHERE key = ANY (removed_keys);
-- Inserting a new update with the new key and value
INSERT INTO af_collab_update(
        oid,
        value,
        encrypt,
        md5,
        value_size,
        partition_key,
        uid,
        workspace_id,
        did
    )
VALUES (
        oid,
        new_value,
        encrypt,
        md5,
        value_size,
        partition_key,
        uid,
        workspace_id,
        did
    );
-- Releasing the lock
PERFORM pg_advisory_unlock(lock_key);
RETURN;
END;
$$ LANGUAGE plpgsql;
```

Then we can call the `flush_collab_updates_v3` function in Rust.

```rust
pub(crate) async fn flush_collab_with_update(
  object: &CollabObject,
  update_items: Vec<UpdateItem>,
  postgrest: &Arc<Postgres>,
  update: Vec<u8>,
  secret: Option<String>,
) -> Result<(), Error> {
  // 2.Merge the updates into one and then delete the merged updates
  let merge_result = spawn_blocking(move || merge_updates(update_items, update)).await??;
  tracing::trace!("Merged updates count: {}", merge_result.merged_keys.len());

  let workspace_id = object
    .get_workspace_id()
    .ok_or(anyhow::anyhow!("Invalid workspace id"))?;

  let value_size = merge_result.new_update.len() as i32;
  let md5 = md5(&merge_result.new_update);

  let (new_update, encrypt) =
    SupabaseBinaryColumnEncoder::encode(merge_result.new_update, &secret)?;
  let params = InsertParamsBuilder::new()
    .insert("oid", object.object_id.clone())
    .insert("new_value", new_update)
    .insert("encrypt", encrypt)
    .insert("md5", md5)
    .insert("value_size", value_size)
    .insert("partition_key", partition_key(&object.ty))
    .insert("uid", object.uid)
    .insert("workspace_id", workspace_id)
    .insert("removed_keys", merge_result.merged_keys)
    .insert("did", object.get_device_id())
    .build();

  postgrest
    .rpc("flush_collab_updates_v3", params)
    .execute()
    .await?
    .success()
    .await?;
  Ok(())
}
```
## Realtime

Using Supabase's [realtime](https://supabase.com/docs/guides/realtime) service, we can track changes to specific tables. For example, monitoring the `af_user` table allows us to capture the most recent user activities whenever they sign in on various devices. Other tables can be monitored in the same way.


![](./uml-Realtime_Service.png)


### Dive in the code

We observe update events from both the `af_collab_update` and `af_user` tables. When an update event is triggered, we propagate the event data to the Rust backend.  

```dart
Future<void> _subscribeTablesChanges() async {
 final List<ChannelFilter> filters = [
      "document",
      "folder",
      "database",
      "database_row",
      "w_database",
    ]
        .map(
          (name) => ChannelFilter(
            event: 'INSERT',
            schema: 'public',
            table: "af_collab_update_$name",
            filter: 'uid=eq.${userProfile.id}',
          ),
        )
        .toList();

    filters.add(
      ChannelFilter(
        event: 'UPDATE',
        schema: 'public',
        table: "af_user",
        filter: 'uid=eq.${userProfile.id}',
      ),
    );

    const ops = RealtimeChannelConfig(ack: true);
    channel?.unsubscribe();
    channel = supabase.client.channel("table-db-changes", opts: ops);
    for (final filter in filters) {
      channel?.on(
        RealtimeListenTypes.postgresChanges,
        filter,
        (payload, [ref]) {
          try {
            final jsonStr = jsonEncode(payload);
            final pb = RealtimePayloadPB.create()..jsonStr = jsonStr;
            UserEventPushRealtimeEvent(pb).send();
          } catch (e) {
            Log.error(e);
          }
        },
      );
    }

    channel?.subscribe(
      (status, [err]) {
        Log.info(
          "subscribe channel statue: $status, err: $err",
        );
      },
    );
 }
```

Different components will consume various updates. A detailed discussion on this is beyond the purview of this documentation, but we will delve into it in future discussions.





