# Agentic Chatbot Setup

This document explains how to set up the necessary credentials for Google Drive and Google Cloud Platform (GCP) authentication.

## Prerequisites
- A Google Cloud Platform (GCP) account.
- A Google Cloud Project with the Google Drive API enabled.

## 1. Setting up Google Drive Server Credentials (`.gdrive-server-credentials.json`)

This file is used for server-to-server authentication (Service Account).

1. Go to the [Google Cloud Console](https://console.cloud.google.com/).
2. Select your project.
3. Navigate to **APIs & Services** > **Credentials**.
4. Click **Create Credentials** and select **Service account**.
5. Fill in the service account details and click **Create and Continue**.
6. (Optional) Grant the service account access to your project.
7. Click **Done**.
8. In the Service Accounts list, click on the newly created service account.
9. Go to the **Keys** tab.
10. Click **Add Key** > **Create new key**.
11. Select **JSON** and click **Create**. The JSON file will be downloaded to your computer.
12. Rename the downloaded file to `.gdrive-server-credentials.json` and place it in the root directory of this repository.

*Note: If you need the service account to access specific folders in your Google Drive, you must share those folders with the service account's email address.*

## 2. Setting up GCP OAuth Keys (`gcp-oauth.keys.json`)

This file is used for user authentication (OAuth 2.0 Client ID).

1. Go to the [Google Cloud Console](https://console.cloud.google.com/).
2. Select your project.
3. Navigate to **APIs & Services** > **OAuth consent screen**.
4. Configure the consent screen (choose External or Internal depending on your needs) and add necessary scopes (e.g., Google Drive API scopes).
5. Go to **APIs & Services** > **Credentials**.
6. Click **Create Credentials** and select **OAuth client ID**.
7. Select the **Application type** (e.g., Web application, Desktop app).
8. If selecting Web application, add the authorized redirect URIs as required by your application.
9. Click **Create**.
10. On the confirmation screen, click **Download JSON** (the download icon).
11. Rename the downloaded file to `gcp-oauth.keys.json` and place it in the root directory of this repository.

## Security Warning
**DO NOT** commit `.gdrive-server-credentials.json` or `gcp-oauth.keys.json` to version control. Ensure they are listed in your `.gitignore` file.
