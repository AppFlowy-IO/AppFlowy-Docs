# Sync Desktop and Mobile

Thank you for helping us test AppFlowy Mobile on either TestFlight or the Play Console. Here is the guide on how to sync data across mobile and desktop devices. Actually, it is part of the AppFlowy Cloud services that we have been working on over the past year.



<mark style="color:red;">**IMPORTANT: Please expand the image below to decide where to get started.**</mark>

<figure><img src="../.gitbook/assets/Decision Tree - Frame 1.jpg" alt=""><figcaption></figcaption></figure>

### Section I: Start fresh

<figure><img src="../.gitbook/assets/IMG_8709 1.png" alt=""><figcaption></figcaption></figure>

We currently support three third-party login options:

* Google
* GitHub
* Discord

Please choose one of the above options to log in.&#x20;

[Download ](https://github.com/AppFlowy-IO/AppFlowy/releases)the latest desktop app (v0.4.1 or above).

Syncing data across devices is easy; simply log in to your desktop app using the same account:

<figure><img src="../.gitbook/assets/image (51).png" alt="" width="375"><figcaption></figcaption></figure>



### Section II: Sync from desktop

[Download ](https://github.com/AppFlowy-IO/AppFlowy/releases)the latest desktop app (v0.4.1 or above).

Begin by backing up the data folder to a safe location.&#x20;

Navigate to 'Settings' -> 'Files', and then click the folder icon next to the 'Change' button.&#x20;

Copy <mark style="color:red;">the folder one level up</mark> (likely called "AppFlowyDoNotRename," as seen in the attached) and paste it into a secure local location, or compress it into a zip file and email the zip file to yourself for safekeeping.

<figure><img src="../.gitbook/assets/Group 1.png" alt=""><figcaption></figcaption></figure>

Now follow the steps below:

1. Go to Settings -> Cloud Settings
2. Set Cloud Server to `AppFlowy Cloud`

<figure><img src="../.gitbook/assets/image (48).png" alt="" width="375"><figcaption></figcaption></figure>

3. Enable sync: toggle it on

<figure><img src="../.gitbook/assets/image (49).png" alt="" width="375"><figcaption></figcaption></figure>

4. Fill in Base URL with [`https://beta.appflowy.cloud`](https://beta.appflowy.cloud)

<figure><img src="../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

5. Click the `Restart` button
6. Once the app has restarted, navigate to 'Settings' -> 'User'.
7. Choose one of the available third-party login options.
8. <mark style="color:red;">Select an account that you have never previously used to log into AppFlowy.</mark> For other scenarios, please refer to Section III: Plan B
9. Allow some time for the app to sync, especially if you have a lot of data in the desktop app.
10. Now go to AppFlowy Mobile and log in using the same account



### Section III: Plan B

Don't worry; we've got you covered. To move your desktop data to the account used on mobile, please follow the steps below:

1. [Download ](https://github.com/AppFlowy-IO/AppFlowy/releases)the latest desktop app (v0.4.1 or above)
2. Open your AppFlowy Desktop application.
3. Navigate to 'Settings' -> 'Files'.
4. Locate your AppFlowy data folder.

On Windows, click the path to copy it to your clipboard, then paste this into your file explorer to access the folder.

<figure><img src="../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>

For Mac users, click the folder icon next to the 'Change' button to open the data folder.

<figure><img src="../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

5. Copy <mark style="color:red;">the folder one level up</mark> (likely called "AppFlowyDoNotRename," as seen in the attached) and paste it into a secure local location
6. Also compress it into a zip file and email the zip file to yourself for safekeeping.&#x20;

<figure><img src="../.gitbook/assets/Group 1 (1).png" alt=""><figcaption></figcaption></figure>

6. Now, return to the desktop app and navigate to 'Settings' -> 'Cloud Settings':\


<figure><img src="../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>



7. Select 'AppFlowy Cloud' as your cloud server option.
8. Enable syncing by toggling 'On'.
9. Enter the base URL: [https://beta.appflowy.cloud](https://beta.appflowy.cloud/)
10. Click the 'Restart' button.
11. Once the app restarts, navigate to 'Settings' -> 'User'.
12. Log in using the same account you used for the mobile version.
13. Go to Settings -> Files
14. Click on 'Import Data from External AppFlowy Folder'.
15. Locate the appflowy data folder copied from step 5
16. Click 'Choose' to start the import.
17. Wait for the process to complete.
18. Now you're all set!

<figure><img src="../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

Congratulations, you're all set! Your data should now be successfully synced across your devices using AppFlowy. If you encounter any issues or have any questions, don't hesitate to reach out on [Discord](https://discord.gg/9Q2xaN37tV) for support. We're more than happy to help!
