# Browser build with Fastlane

A browser build uses GitHub Actions and Fastlane to build xDrip4iOS and upload it to your own App Store Connect account. You do not need a Mac.

This method allows you to:

- install xDrip4iOS through TestFlight
- send builds and updates to people you support
- reinstall the app using only TestFlight if a phone is replaced or the app is deleted
- build with the Xcode version configured by the xDrip4iOS project.

The initial setup takes some time, but most steps are completed only once. After the first successful build, scheduled builds keep a current version available in TestFlight.

## What you need

- a [GitHub account](https://github.com/signup)
- a paid [Apple Developer Program](https://developer.apple.com/programs/) membership
- access to [App Store Connect](https://appstoreconnect.apple.com/)
- about two hours for the initial setup.

If you already use browser builds for Loop, Loop Follow, Trio, iAPS, or another compatible app, you can reuse most of the Apple and GitHub details created for that app.

!!! info
    TestFlight builds expire after 90 days. The default xDrip4iOS automation creates a new build at least once a month after setup is complete.

## Automatic builds

The default automation:

- checks for xDrip4iOS updates every Wednesday at 08:00 UTC and builds when an update is found
- creates a new build on the first day of every month at 06:00 UTC, even when there is no app update
- updates the fork before an automatic build unless automatic synchronisation has been disabled
- maintains an `alive` branch so GitHub does not disable scheduled Actions because of repository inactivity.

A successful **Build xDrip4iOS** run does not always mean that a new app was built. A short scheduled run can finish after checking for updates. A run that creates and uploads an app takes longer.

## Save the six secrets

The build uses six case-sensitive secrets. Four come from Apple and two are created through GitHub.

| Secret | Source |
| --- | --- |
| `TEAMID` | Apple Developer account |
| `FASTLANE_ISSUER_ID` | App Store Connect API key |
| `FASTLANE_KEY_ID` | App Store Connect API key |
| `FASTLANE_KEY` | Downloaded App Store Connect API private key |
| `GH_PAT` | GitHub personal access token |
| `MATCH_PASSWORD` | A password that you create |

Save these values in a plain-text file while completing the setup. Do not use an editor that can change capitalisation or replace characters.

!!! warning
    These secrets provide access to your Apple Developer and GitHub accounts. Do not share them, add them to a public repository, or include them in screenshots.

## Create an App Store Connect API key

This creates the four Apple secrets. If you already created an App Store Connect API key for another browser-built app, you can reuse its details.

1. Open [Certificates, Identifiers & Profiles](https://developer.apple.com/account/resources/certificates/list).
2. Copy the **Team ID** shown for your developer account and save it as `TEAMID`.
3. Open [App Store Connect API keys](https://appstoreconnect.apple.com/access/api).
4. Create a key with **Admin** access and name it `FastLane API Key`.
5. Save the Issuer ID as `FASTLANE_ISSUER_ID`.
6. Save the Key ID as `FASTLANE_KEY_ID`.
7. Download the private key file. Apple allows this file to be downloaded only once.
8. Open the file in a plain-text editor and copy all of its contents, including the `-----BEGIN PRIVATE KEY-----` and `-----END PRIVATE KEY-----` lines. Save this as `FASTLANE_KEY`.

## Create a GitHub personal access token

If you already use browser builds for another app, you can reuse the same `GH_PAT`.

1. Create a [classic personal access token](https://github.com/settings/tokens/new).
2. Enter `FastLane Access Token` as its name.
3. Select **No expiration**.
4. Select the `workflow` scope. GitHub will also select the required `repo` permissions.
5. Select **Generate token**.
6. Copy the token immediately and save it as `GH_PAT`.

The token must include the `workflow` scope for automatic repository updates and scheduled builds.

## Create the Match password

Create a strong password and save it as `MATCH_PASSWORD`. Fastlane uses it to protect the signing files stored in your private Match-Secrets repository.

Keep this password. If it is lost, you will need to delete the Match-Secrets repository and create the signing files again.

## Fork the xdripswift repository

1. Open the official [xdripswift repository](https://github.com/JohanDegraeve/xdripswift).
2. Select **Fork**.
3. Create the fork in your GitHub account or in a GitHub organisation that you control.

A GitHub organisation is useful when you build several compatible apps. Shared organisation secrets can then be made available to each selected repository.

## Add the secrets to GitHub

If the fork belongs to your personal account:

1. Open the fork.
2. Select **Settings > Secrets and variables > Actions**.
3. Open the **Secrets** tab.
4. Add each of the following as a repository secret:
   - `TEAMID`
   - `FASTLANE_ISSUER_ID`
   - `FASTLANE_KEY_ID`
   - `FASTLANE_KEY`
   - `GH_PAT`
   - `MATCH_PASSWORD`.

If the fork belongs to an organisation, add the same Actions secrets in the organisation settings and allow the xdripswift repository to use them.

Do not create `ENABLE_NUKE_CERTS` for xDrip4iOS. Certificate renewal is explained later on this page.

## Validate the secrets

1. Open the **Actions** tab of your xdripswift fork.
2. Enable GitHub Actions if prompted.
3. Select **1. Validate Secrets**.
4. Select **Run workflow**, then select the green **Run workflow** button.
5. Wait for the workflow to finish with a green check mark.

Open the failed run and read its log if an error is shown. GitHub can take a short time to display a newly started or completed workflow, so refresh the page if its status does not change.

## Add the Apple identifiers

1. Open the **Actions** tab of the fork.
2. Select **2. Add Identifiers**.
3. Select **Run workflow**, then select the green **Run workflow** button.
4. Wait for the workflow to finish with a green check mark.

This creates the bundle identifiers needed by the app and its extensions.

## Create the App Groups

xDrip4iOS uses App Groups to share data with its extensions and compatible open-source AID apps.

### Loop App Group

Skip this section if you previously built xDrip4iOS or Loop with the same Apple Developer account.

1. Open [Register an App Group](https://developer.apple.com/account/resources/identifiers/applicationGroup/add/).
2. Enter `Loop App Group` as the description.
3. Enter `group.com.TEAMID.loopkit.LoopGroup` as the identifier, replacing `TEAMID` with your Apple Team ID.
4. Select **Continue**, then **Register**.

### Trio App Group

Skip this section if you previously built xDrip4iOS or Trio with the same Apple Developer account.

1. Open [Register an App Group](https://developer.apple.com/account/resources/identifiers/applicationGroup/add/).
2. Enter `Trio App Group` as the description.
3. Enter `group.org.nightscout.TEAMID.trio.trio-app-group` as the identifier, replacing `TEAMID` with your Apple Team ID.
4. Select **Continue**, then **Register**.

## Add the App Groups to the identifiers

Open [Certificates, Identifiers & Profiles](https://developer.apple.com/account/resources/identifiers/list). Configure each identifier created by the workflow.

| Name | Identifier |
| --- | --- |
| xdrip | `com.TEAMID.xdripswift` |
| xDrip Notification Context Extension | `com.TEAMID.xDripNotificationContextExtension` |
| xDrip Watch App | `com.TEAMID.xdripswift.watchkitapp` |
| xDrip Watch Complication Extension | `com.TEAMID.xdripswift.watchkitapp.xDripWatchComplication` |
| xDrip Widget Extension | `com.TEAMID.xdripswift.xDripWidget` |

For each identifier:

1. Select the identifier.
2. Find **App Groups** and select **Configure**.
3. Select **Loop App Group**.
4. For the main `xdrip` identifier, also select **Trio App Group**.
5. Select **Continue**, **Save**, then **Confirm**.

The displayed names can differ if the identifiers were created by an earlier Xcode build. Match them using the identifier values.

## Create the App Store Connect app

Skip this section if this Apple Developer account already has an App Store Connect app using `com.TEAMID.xdripswift`.

1. Open [Apps](https://appstoreconnect.apple.com/apps) in App Store Connect.
2. Select the blue add button and choose **New App**.
3. Select **iOS**.
4. Enter a unique App Store Connect name. This does not change the `xDrip4iOS` name shown on the phone.
5. Select the primary language.
6. Select the bundle ID matching `com.TEAMID.xdripswift`.
7. Enter an SKU, such as `123`.
8. Select **Full Access**, then select **Create**.

The remaining App Store submission details are not required for internal TestFlight testing.

## Create the signing certificates

1. Return to the **Actions** tab of the xdripswift fork.
2. Select **3. Create Certificates**.
3. Select **Run workflow**, then select the green **Run workflow** button.
4. Wait for the workflow to finish with a green check mark.

This workflow creates or reuses the Apple Distribution certificate, creates the required provisioning profiles, and stores the encrypted signing files in a private Match-Secrets repository. GitHub creates this repository automatically when it is first needed.

Do not edit, rename, or make the Match-Secrets repository public.

## Build xDrip4iOS

1. Open the **Actions** tab of the fork.
2. Select **4. Build xDrip4iOS**.
3. Select **Run workflow**, then select the green **Run workflow** button.
4. Wait for the workflow to build and upload the app.
5. Open [Apps](https://appstoreconnect.apple.com/apps) in App Store Connect and wait for Apple to process the build.

The first build can take some time. Open the workflow log if it finishes with a red error.

## Add TestFlight users

For each person who will install this build:

1. Add the person in [Users and Access](https://appstoreconnect.apple.com/access/users) in App Store Connect.
2. Open the xDrip4iOS app in App Store Connect.
3. Open **TestFlight** and create or select an internal testing group.
4. Add the processed build to that group.
5. Add the App Store Connect user to the group.

The invited person can then install or update xDrip4iOS using Apple's TestFlight app. See [Install with TestFlight](testflight.md) for the installation steps.

In the United States, the Apple Account holder must be at least 13 years old to install with TestFlight. For a younger user, an adult must sign in to **Media & Purchases** on the child's phone. See [TestFlight for a child](https://loopkit.github.io/loopdocs/browser/phone-install/#testflight-for-a-child) for more information.

For more details, see [TestFlight overview](https://loopkit.github.io/loopdocs/browser/tf-users/) and [Install on phone](https://loopkit.github.io/loopdocs/browser/phone-install/) in LoopDocs.

## The alive branch

GitHub can disable scheduled Actions after 60 days without repository activity. The xDrip4iOS workflow creates an `alive` branch and adds an occasional keep-alive commit to it.

Do not delete, rename, or modify the `alive` branch. It is not used to build the app.

## Annual certificate renewal

Apple Distribution certificates expire. Apple normally sends an email before the current certificate expires.

If you also build Loop, Trio, or another app that automatically renews the shared certificate, build that app first after the old certificate has been removed. Then run **3. Create Certificates** for xDrip4iOS.

If xDrip4iOS is the only app you build this way, wait until the old certificate has expired and Apple has removed it. Delete the private Match-Secrets repository, then run **3. Create Certificates** again. See [Delete Match Secrets](https://loopkit.github.io/loopdocs/browser/bb-errors/#delete-match-secrets) for more information.

## Change the automatic build behaviour

The default settings are recommended. You can change them by adding repository variables.

| `SCHEDULED_SYNC` | `SCHEDULED_BUILD` | Automatic behaviour |
| --- | --- | --- |
| `true` or not set | `true` or not set | Keep alive, check for updates weekly, and build monthly |
| `true` or not set | `false` | Keep alive, check weekly, and build only when an update is found |
| `false` | `true` or not set | Keep alive and build monthly without updating the fork |
| `false` | `false` | No automatic update, build, or keep-alive activity |

To add a variable:

1. Open the xdripswift fork.
2. Select **Settings > Secrets and variables > Actions**.
3. Open the **Variables** tab.
4. Select **New repository variable**.
5. Enter `SCHEDULED_BUILD` or `SCHEDULED_SYNC` as the name.
6. Enter `false` as the value.
7. Select **Add variable**.

!!! warning
    Disabling scheduled builds can allow the current TestFlight build to expire. Run **4. Build xDrip4iOS** manually before the 90-day TestFlight period ends.

## If a build fails

- Open the failed Action and read the first useful error in its log.
- Run **1. Validate Secrets** again after changing a secret.
- Confirm that `GH_PAT` includes both the `repo` and `workflow` scopes.
- Confirm that all five identifiers have the required App Groups.
- Confirm that the App Store Connect app uses the correct main bundle ID.
- Do not delete the Match-Secrets repository unless certificate renewal or signing recovery requires it.

See [Browser build errors](https://loopkit.github.io/loopdocs/browser/bb-errors/) in LoopDocs for additional GitHub Actions, Fastlane, certificate, and TestFlight troubleshooting.
