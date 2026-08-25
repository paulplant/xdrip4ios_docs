# Update and back up

Update xDrip4iOS through the same distribution path used for installation.

## Before an update

- Open **Settings**, scroll to **Data Management**, and select **Create Backup**.
- Confirm that the new build comes from the same trusted publisher or your own source configuration.
- Keep Nightscout or another independent data path available if continuity is important.
- Do not delete the current app to install an update unless the publisher explicitly requires it.

Installing over the existing app with the same bundle identifier normally preserves app data. Deleting the app removes its local data and settings.

For backup contents, encryption, and restore choices, see [Data Management](../use/dataManagement.md).

## TestFlight

Open TestFlight and install the new build. TestFlight displays the expiry of the installed build.

## Source build

Pull the latest source, preserve `xDripConfigOverride.xcconfig`, review changes, and build with the same bundle identifier and signing configuration. See [Build from source](build.md).

## After an update

1. Open xDrip4iOS.
2. Confirm the version under **Settings > About xDrip4iOS**.
3. Confirm the current glucose and timestamp.
4. Confirm Bluetooth or follower status.
5. Test important alerts and integrations.
6. Open the Watch app, widgets, and Live Activity if you use them.
