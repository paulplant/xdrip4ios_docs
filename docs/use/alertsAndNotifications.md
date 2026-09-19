# Alerts and Notifications

xDrip4iOS separates alarms from iOS notification display options.

## Alarm Types

An Alarm Type defines how an alarm behaves, including its sound and repetition. Create or edit Alarm Types before assigning them to scheduled alarms.

An Alarm Type contains:

- **Enabled**, which makes the type available to its assigned alarms
- **Name**, which identifies it in the alarm list
- **Vibrate**
- **Sound**, including no sound, the default iOS sound, or an included xDrip4iOS sound
- **Override Mute**, which requests sound even when the mute switch is active
- **Snooze Via Notification**
- **Default Snooze Time**.

Selecting a sound in the picker plays a preview. An Alarm Type cannot be deleted while an alarm still uses it. Disable it or assign a different type to those alarms first.

**Override Mute** still depends on iOS allowing the app and audio session to run. Test it on the device instead of assuming that it will always override every system state.

Use the volume tests to compare xDrip4iOS sound playback with normal iOS notification playback. Test at a safe time and volume.

## Alarms

Alarms can cover:

- urgent low
- low
- high
- urgent high
- fast fall
- fast rise
- missed reading or disconnection
- Not Looping, when compatible AID status is received from Nightscout
- calibration reminder
- transmitter battery, when supported
- sensor or transmitter failure
- iPhone battery.

Each alarm has a start time, trigger value or rate where applicable, and Alarm Type. Add more than one alarm when different times of day need different behaviour. Disable an alarm instead of deleting it when you may need it later.

The first alarm in a scheduled group begins at midnight. Add another alarm to change the threshold or Alarm Type later in the day. Each added alarm applies from its start time until the next alarm in that group begins.

Some alarms are event-based and do not use a daily schedule. They have one all-day entry and show only the controls that apply to that event.

Disabling an alarm disables the complete alarm group. Deleting a later scheduled entry removes only that part of the schedule.

The low iPhone battery alarm is not shown while the iPhone is charging.

Dexcom G6 and G7-family devices use separate battery assessments. The alarm editor identifies the active setting as **Battery Low (G6)** or **Battery Low (G7)**. Changing one does not replace the saved threshold for the other family.

When you go back after changing an alarm, xDrip4iOS asks whether to **Save** or **Discard Changes**. This prevents an accidental back gesture from losing the changes.

**Large Snooze Screen** uses larger controls when an active alarm opens the snooze picker automatically. It is enabled by default. Disable it to use the standard-size picker. The normal Snooze screen opened from the Home toolbar is not changed. The same option is available under **Quick Show/Hide > Additional Items**.

### Not Looping

The **Not Looping** alarm warns when a connected AID system has not reported a recent successful loop cycle. Set the number of minutes allowed since the last loop and assign an Alarm Type.

This alarm only works while Nightscout is enabled with a follow type that provides current device status. It does not warn when the Nightscout information itself is too old, because the app cannot then confirm the current state of the AID system. Use a **Missed Readings** alarm and the AID system's own safety alerts as well.

The **Not Looping** alarm is disabled by default.

## Sensor health warnings

xDrip4iOS can show a warning on **Home** when it detects prolonged sensor noise, an unchanged sensor signal, a temporary sensor issue, a sensor failure, or a transmitter failure. Select the warning to open the relevant Sensor or device screen. The warning can be dismissed after it has been reviewed.

**Sensor Health Warnings** under **Settings > Alerts and Notifications** controls optional iOS notifications for prolonged sensor noise, an unchanged signal, and temporary sensor issues. The warning on **Home** remains available when these notifications are disabled.

Sensor and transmitter failures use the separate **Sensor/Transmitter Failure** alarm. Configure its Alarm Type with the other alarms.

## Reading notifications

Under **Settings > Alerts and Notifications > Notifications**, configure:

- whether a glucose reading appears in notifications
- the minimum notification interval
- Live Activity display type
- whether available IOB and COB are shown in supported Live Activity layouts
- a preview of the selected Live Activity layout
- CarPlay style and preview on iOS 26 or later
- whether the app badge shows a reading
- whether a badge value is multiplied by ten for mmol/L display compatibility.

Live Activities are available in Master mode. In Follower mode, they are available only when **Keep-alive** is set to **Heartbeat** and a heartbeat device is connected.

When a Live Activity is enabled on iOS 26 or later, the **CarPlay** section provides **Chart** and **Basic** styles. **Chart** includes the recent glucose chart. **Basic** shows a larger glucose value without the chart. The selected style can also affect the Apple Watch Smart Stack because Apple uses the same compact Live Activity layout for both displays.

Press and hold an eligible xDrip4iOS notification to open its expanded view. Glucose and relevant sensor alerts can show the current glucose, trend, delta, units, and a short chart. Other alerts use a text-only expanded view.

The notification interval limits routine glucose notifications. It does not change the CGM reading interval or the schedule of configured alarms.

## If an alarm is not heard

Check the alarm, Alarm Type, app notification permission, iPhone volume, mute switch, Focus mode, connected audio devices, and reading age. See [Alarms and background operation](../troubleshoot/background.md).

!!! warning
    xDrip4iOS cannot guarantee that an alarm will sound. iOS settings, a force-quit app, Bluetooth, internet access, and device power can delay or prevent alarms. Keep the safety methods recommended for your CGM system.
