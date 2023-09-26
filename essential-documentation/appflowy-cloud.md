# ☁ AppFlowy Cloud

## It's on a private beta mode. You have the chance to be among the first to experience it. Sign up [here](https://survey.appflowy.io/private-beta).



## AppFlowy Cloud does four things for you:&#x20;

1. Allows you to back up local data and access it from different devices&#x20;
2. Given that AppFlowy is privacy-first, you can opt for end-to-end encryption, ensuring utmost privacy and security of your data&#x20;
3. You will have the flexibility to remain local and sync as required&#x20;
4. Provides you with the freedom to make one workspace 100% local and another backed up to the cloud\


## New to AppFlowy

If you're new to AppFlowy, click the button below labeled "Or continue with." This will create a new account for you.

<div align="center">

<figure><img src="../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

</div>

For example, clicking the Google button will navigate you to the web browser for authentication.



<figure><img src="../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>



## Already with AppFlowy

If you've been using AppFlowy for some time, you can migrate your local data to AppFlowy Cloud. Navigate to Settings -> User -> Sign in with Google. After signing in, your local data will sync to your account.

<figure><img src="../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

## Data encryption

To enable end-to-end encryption, navigate to Settings -> Sync Settings -> Toggle on Encrypt data. Once it is enabled, it can not be turned off. Ensure you store your encryption key securely.&#x20;

As of now, AppFlowy saves the key on your local disk. If you delete AppFlowy's data folder, you will lose the encryption key, making it impossible to decrypt your data

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>



## FAQ 🤔

### How to sign in on other devices after enabling data encryption?

> When data encryption is enabled, the sign-in process will differ. It will require you to enter the encryption secret. You must provide the correct secret; otherwise, the sign-in will not be successful.

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

### What if I lose my encryption key? <a href="#what-if-i-lose-my-encryption-key" id="what-if-i-lose-my-encryption-key"></a>

> When using data encryption, it is essential you save your encryption key in a secure location.If the key is lost, encrypted journal stored in the AppFlowy cannot be decrypted. AppFlowy does not have access to the private key at any point.

### What happens when encryption is enabled on one device while some other devices are already logged in?

> Enabling encryption on one device will force other devices that previously logged in without the encryption key to log out. They will then need to log in again using the encryption key

### Can I log in using other third-party OAuth authentication?

> We plan to support additional authentication methods in the future. Let us know if you have specific preference

### Can I self-host AppFlowy with cloud functionality enabled?

> Of course! The documentation for self-hosting is still in progress, but once it's complete, the setup will be quite straightforward for developers. Just a single command and you're all set

### Can I use other cloud storage services as remote storage for AppFlowy?

> Any cloud storage that supports key/value storage can be used as remote storage for AppFlowy. For instance, AWS.&#x20;

