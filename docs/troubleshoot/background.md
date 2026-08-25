# Alarms and background operation

Use this page when the Home tab updates but alarms, Follower downloads, widgets, or other background features do not.

## iOS checks

1. Enable xDrip4iOS under **Settings > Notifications**.
2. Enable **Background App Refresh** for xDrip4iOS.
3. Do not force-quit xDrip4iOS.
4. Check Low Power Mode.
5. Check Focus mode, mute switch, volume, and the current audio route.
6. Open xDrip4iOS and confirm that the source reading itself is current.

## Alarm checks

Confirm that the alarm is enabled for the current time, its threshold was crossed, and its Alarm Type has a valid sound. Use both volume tests under **Settings > Alerts and Notifications > Alarms**.

## Follower background updates

The Normal and Aggressive **Keep-alive** options under **Settings > Data Source** try to keep follower updates running in the background. Start with Normal and use Aggressive only when Normal is not reliable enough.

Continuous plays silent audio continuously while the app is in the background. It has the highest battery use and should only be used in extreme cases when Normal and Aggressive do not work well enough. It cannot guarantee that iOS will keep the app active.

Heartbeat requires a connected heartbeat device. iOS decides when background work can run, regardless of the selected option.

## Widgets, Watch, and Live Activity

Widgets, Apple Watch, and Live Activities update separately from the main app and can show an older value. Open xDrip4iOS first. If the main reading is current, open or re-add the affected item. Compare its reading time with **Home**.

In Follower mode, widgets and xDrip4iOS Watch complications show a warning when **Keep-alive** is **Disabled**. This prevents an old glucose value from looking current. Select Normal, Aggressive, Continuous, or Heartbeat under **Settings > Data Source > Keep-alive** if background display is required.
