# Database

AppFlowy use [SQLite](https://www.sqlite.org/index.html) as database and [Diesel](https://diesel.rs/) as [ORM](https://en.wikipedia.org/wiki/Object%E2%80%93relational_mapping).
The crate, flowy-database, contains the logic for crating the SQLite [schema](https://www.sqlite.org/schematab.html) and prividing a shared kv storage.

## The flowy-database
![flowy-database.png](../../../../.gitbook/assets/flowy-database.png)

flowy-database is located in `frontend/rust-lib/flowy-database`. The following section will guide you through how to 
create a schema. Before starting, I recommend checking out the [Diesel Getting Started](https://diesel.rs/guides/getting-started) if you don't know about
diesel before. Make sure you install the diesel CLI tool. You can install it by running:
> cargo install diesel_cli --no-default-features --features sqlite


### Relation Graph


### Create schema

Create a new schema.
```shell
cd frontend/rust-lib/flowy-database/
diesel migration generate user-add-icon
```

**Output**
* Creating migrations/2022-08-07-140433_user-add-icon/up.sql
* Creating migrations/2022-08-07-140433_user-add-icon/down.sql

Migrations allow us to evolve the database schema over time. Each migration can be 
applied (up.sql) or reverted (down.sql). Applying and immediately reverting a migration
should leave your database schema unchanged.


Open the up.sql
```SQL
ALTER TABLE user_table ADD COLUMN icon_url TEXT NOT NULL DEFAULT '';
```

Open the down.sql
```SQL
ALTER TABLE user_table DROP COLUMN icon_url;
```


```SQL
diesel migration run
```

The icon_url is added to the user_table schema automatically.

```rust
// flowy-database/src/schema.rs
table! {
    user_table (id) {
        id -> Text,
        name -> Text,
        token -> Text,
        email -> Text,
        workspace -> Text,
        icon_url -> Text,
    }
}
```

## Write Rust
