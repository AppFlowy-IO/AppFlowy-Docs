# ☁️ Self-hosting AppFlowy with AppFlowy Cloud

AppFlowy is a privacy-first, open-source workspace designed for notes, wikis, projects, and more, giving you full control over your data and customizations. Over the past year, our community-driven approach has focused on delivering a data-privacy-centric, reliable native experience, and extensible platform.

We're thrilled to introduce self-hosting capabilities for AppFlowy, further empowering users to tailor workspaces to their needs. This guide is divided into two key sections:

1. Setting up AppFlowy Cloud on your server.
2. Building AppFlowy with a self-hosted server.

🙏If you have any questions, don't hesitate to contact us on [Discord](https://discord.gg/7kmZgcvA).

## Step 1: Setting Up AppFlowy Cloud

To self-host AppFlowy Cloud, please refer to our comprehensive [deployment guide](https://github.com/AppFlowy-IO/AppFlowy-Cloud/blob/main/doc/deployment.md).

## Step 2: Building AppFlowy with a Self-hosted Server

> 💪This step will become unnecessary once the AppFlowy client application is updated to allow switching between self-hosted servers directly within the app.

### Fork the Repository

- Visit the [AppFlowy-Cloud Build repository](https://github.com/AppFlowy-IO/AppFlowy-with-AppFlowy-Cloud-Build) on GitHub.
- Click "Fork" to create your version of the repository.

### Configure Environment Secrets

- In your forked repository, go to "Settings" > "Environments".
- Create a new environment named `AppFlowyCloud`.
- Add these secrets under "Add secret":
    - `CLOUD_TYPE`: `2` (indicating AppFlowy Cloud usage)
    - `APPFLOWY_CLOUD_BASE_URL`: `http://<your-server-hostname>:8000`
    - `APPFLOWY_CLOUD_WS_BASE_URL`: `ws://<your-server-hostname>:8000/ws`
    - `APPFLOWY_CLOUD_GOTRUE_URL`: `http://<your-server-hostname>:9998`
- Replace `<your-server-hostname>` with your server's public hostname or domain name.

![img.png](../assets/appflowy_cloud_self_host_env.png)

### Initiate Deployment

To begin the deployment of AppFlowy, create and push a new release tag using the following commands:

```bash
# Create and push a tag for building AppFlowy version 0.3.8 on the main branch
git tag 0.3.8_main && git push origin 0.3.8_main
```

After pushing the tag, you can view the build process in the Actions tab of your repository.

![appflowy_cloud_build_action.png](../assets/appflowy_cloud_build_action.png)

After the build process is completed, you can download the binaries from the "Assets" section of the build.

![build_artifact.png](../assets/build_artifact.png)

After logging in, you can visit the "Settings" page to confirm that the server URL is correct.

![server_url.png](../assets/setting_server_url.png)


## Current Limitations

**Bundle ID Conflict**

The AppFlowy App built with AppFlowy Cloud currently shares the same bundle ID as the official AppFlowy App. Consequently,
you cannot install both versions on the same device simultaneously. We are working on a solution for this issue.

**Ongoing Development of Stable Branch**

The process of building AppFlowy with AppFlowy Cloud using the stable branch is ongoing. Rapid developments and frequent 
updates in [AppFlowy Cloud](https://github.com/AppFlowy-IO/AppFlowy-Cloud) mean that new features are constantly being added. 