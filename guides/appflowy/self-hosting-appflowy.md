# ☁ Self-hosting AppFlowy with AppFlowy Cloud

AppFlowy is a privacy-first, open source workspace for your notes, wikis, projects, and more. You are in charge of your data and customizations, with no vendor lock-in.

Over the past year, we've been working hard alongside thousands of community members towards our mission: to empower everyone to create workspaces that suit their needs, without limits on what's possible. We have been determined to uphold our three core values from the very beginning:

* Data privacy first
* Reliable native experience
* Community-driven extensibility

We're excited to announce that AppFlowy now supports self-hosting. This article provides an in-depth look and instructions on how to self-host AppFlowy alongside [AppFlowy Cloud](https://github.com/AppFlowy-IO/AppFlowy-Cloud). This article is divided into two parts:

1. Self-host [AppFlowy Cloud](https://github.com/AppFlowy-IO/AppFlowy-Cloud)
2. Build AppFlowy with Self-hosted server

## Self-host AppFlowy Cloud

Follow this [guide](https://github.com/AppFlowy-IO/AppFlowy-Cloud/blob/main/doc/deployment.md) you will be able to self-host AppFlowy Cloud in AWS EC2.

## Build AppFlowy with a Self-hosted Server

1. **Fork the Repository**:
   * Navigate to the [AppFlowy with AppFlowy-Cloud Build repository](https://github.com/AppFlowy-IO/AppFlowy-with-AppFlowy-Cloud-Build) on GitHub.
   * Click the "Fork" button to create a personal copy of the repository.
2. **Set Up Environment Secrets**:
   * Within your forked repository, go to "Settings" and then select "Environments" from the left sidebar.
   * Click "New environment" to establish an environment named `AppFlowyCloud`.
   * Add the requisite environment secrets by selecting "Add secret":
     * `CLOUD_TYPE`: `2`
     * `APPFLOWY_CLOUD_BASE_URL`: `http://203.0.113.0:8000`
     * `APPFLOWY_CLOUD_WS_BASE_URL`: `ws://203.0.113.0:8000/ws`
     * `APPFLOWY_CLOUD_GOTRUE_URL`: `http://203.0.113.0:9998`

Substitute `203.0.113.0` with your cloud server's actual public IP address. If you have assigned a domain name to your server, use it in place of the IP address.

3.  **Deploy**: Start the deployment by issuing a new tag with the shell command below. The building of the native AppFlowy application and its upload to the release page may take some time.

    ```bash
    git tag -a v0.3.8 -m "Release 0.3.8" && git push origin v0.3.8
    ```
