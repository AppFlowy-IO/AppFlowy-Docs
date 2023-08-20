# ☁ AppFlowy Cloud

## Here comes this AppFlowy Cloud that does 3 things for you:

1. Allow you to back up local data and access it from different devices
2. Given that AppFlowy is local-first, you enjoy the flexibility to remain local and sync as required
3. You have the freedom to make one workspace 100% local and another has cloud backup

## New to AppFlowy

If you're new to AppFlowy, click 'Continue with Google.' This will create a new account for you.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## Already with AppFlowy

If you've been using AppFlowy for some time, you can migrate your local data to AppFlowy Cloud. Navigate to Settings -> User -> Sign in with Google. After signing in, your local data will sync to your account.

<figure><img src="../.gitbook/assets/appflowy_cloud_server_login.png" alt=""><figcaption><p>appflowy server sync</p></figcaption></figure>

## Encrypt your data

Data stored in AppFlowy Cloud is not encrypted by default. To enable encryption, navigate to Settings -> Sync Settings -> Toggle encryption. Once encryption is enabled, it can not be turned off. Ensure you store your encryption key securely. As of now, AppFlowy saves the key on your local disk. If you delete AppFlowy's data folder, you will lose the encryption key, making it impossible to decrypt your data

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

## Sign in on other devices

When data encryption is enabled, the sign-in process will differ. It will require you to enter the encryption secret. You must provide the correct secret; otherwise, the sign-in will not be successful.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

## FAQ

### What if I lose my encryption key? <a href="#what-if-i-lose-my-encryption-key" id="what-if-i-lose-my-encryption-key"></a>

When using data encryption, it is essential you save your encryption key in a secure location.If the key is lost, encrypted journal stored in the AppFlowy cannot be decrypted. AppFlowy does not have access to the private key at any point.



