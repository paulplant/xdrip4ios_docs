# Troubleshooting

Start with the problem that you can see. Do not delete the app or Bluetooth device before checking the connection and recording the error.

## No current reading

Use [No readings or disconnections](connectionProblems.md) for direct Bluetooth sources and general stale-reading checks.

## Follower source does not update

Use [Follower and service problems](follower.md) for Nightscout, Dexcom Share, Shared Calendar, CareLink, LibreLinkUp, and Medtrum EasyView.

## An alert, widget, or background feature did not update

Use [Alarms and background operation](background.md).

## App behaviour is incorrect or reproducible

Use [How to ask for help](reportingIssues.md) to describe your CGM or system, your setup, and what is going wrong. Send an Issue Report only when an xDrip4iOS developer asks for one.

## Understand what happened recently

Open **Settings**, scroll to **Troubleshooting**, then select **Activity Log**. The [Activity Log](activityLog.md) shows useful activity from up to the previous 24 hours, including failures and recoveries. Copy or share it when you need to provide recent context to support.

## Safe first checks

1. Check the latest reading timestamp.
2. Open **Settings > Troubleshooting > Activity Log** and note the time of the problem.
3. Check the data source section at the bottom of the **Home** screen, then select the device in the **Devices** tab and check its connection.
4. Confirm Bluetooth or internet access, depending on the source.
5. Bring xDrip4iOS to the foreground for one normal reading interval.
6. Confirm iOS permissions and battery state.
7. Record the exact error before changing settings.

Restarting the iPhone is a reasonable recovery step after recording the state. Reinstalling is not a first troubleshooting step because it removes local configuration and history.

Before reinstalling or making a large change to stored data, open **Settings**, scroll to **Data Management**, and select **Create Backup**.
