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
- **Repeat Sound**, which repeats an eligible immediate alarm until it is acknowledged or snoozed
- **Snooze Via Notification**
- **Default Snooze Time**.

The editor groups these choices under **Sound** and **Snooze**. Select **Preview Alert** to play or pause the current sound and vibration choices. Selecting a sound in the picker also plays a short preview.

**Repeat Sound** is available when **Override Mute** is enabled and an xDrip4iOS sound is selected. Vibration also repeats when **Vibrate** is enabled. Missed Reading, sensor expiry, and sensor or transmitter failure alerts play once even when their Alarm Type has Repeat Sound enabled.

An Alarm Type cannot be deleted while an alarm still uses it. Disable it or assign a different type to those alarms first.

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
- sensor ending soon
- expected sensor expiry
- iPhone battery.

Each alarm has a start time, trigger value or rate where applicable, and Alarm Type. Add more than one alarm when different times of day need different behaviour. Disable an alarm instead of deleting it when you may need it later.

The first alarm in a scheduled group begins at midnight. Add another alarm to change the threshold or Alarm Type later in the day. Each added alarm applies from its start time until the next alarm in that group begins.

Some alarms are event-based and do not use a daily schedule. They have one all-day entry and show only the controls that apply to that event.

Disabling an alarm disables the complete alarm group. Deleting a later scheduled entry removes only that part of the schedule.

The low iPhone battery alarm is not shown while the iPhone is charging.

### Sensor expiry reminders

**Sensor Ending Soon** sends a reminder before the expected sensor expiry. Set **Hours before expiry** to a whole number from 1 to 48.

**Expected Sensor Expiry** sends a reminder when the expected expiry time is reached.

Both reminders are disabled by default. They work only when the current data source provides an expected sensor expiry. Assign an Alarm Type to each reminder and enable it when required. A sensor change or a changed expiry time updates the scheduled reminder.

Dexcom G6 and G7-family devices use separate battery assessments. The alarm editor identifies the active setting as **Battery Low (G6)** or **Battery Low (G7)**. Changing one does not replace the saved threshold for the other family.

When you go back after changing an alarm, xDrip4iOS asks whether to **Save** or **Discard Changes**. This prevents an accidental back gesture from losing the changes.

**Large Snooze Screen** uses larger controls when an active alarm opens the snooze picker automatically. It is enabled by default. Disable it to use the standard-size picker. The normal Snooze screen opened from the Home toolbar is not changed. The same option is available under **Quick Show/Hide > Alerts and Speech**.

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
- whether the Live Activity is enabled
- Minimal, Normal, or Large Live Activity style
- whether available IOB and COB are shown in supported Live Activity layouts
- a preview of the selected Live Activity layout
- CarPlay style and preview on iOS 26 or later
- whether the app badge shows a reading
- whether a badge value is multiplied by ten for mmol/L display compatibility.

Live Activities are available in Master mode. In Follower mode, they are available only when **Keep-alive** is set to **Heartbeat** and a heartbeat device is connected.

Disabling the Live Activity keeps the selected style. The same enable switch is available under **Quick Show/Hide** on Home.

When a Live Activity is enabled on iOS 26 or later, the **CarPlay** section provides **Chart** and **Basic** styles. **Chart** includes the recent glucose chart. **Basic** shows a larger glucose value without the chart. The selected style can also affect the Apple Watch Smart Stack because Apple uses the same compact Live Activity layout for both displays.

Press and hold an eligible xDrip4iOS notification to open its expanded view. Glucose and relevant sensor alerts can show the current glucose, trend, delta, units, and a short chart. Other alerts use a text-only expanded view.

The notification interval limits routine glucose notifications. It does not change the CGM reading interval or the schedule of configured alarms.

## If an alarm is not heard

Check the alarm, Alarm Type, app notification permission, iPhone volume, mute switch, Focus mode, connected audio devices, and reading age. See [Alarms and background operation](../troubleshoot/background.md).

!!! warning
    xDrip4iOS cannot guarantee that an alarm will sound. iOS settings, a force-quit app, Bluetooth, internet access, and device power can delay or prevent alarms. Keep the safety methods recommended for your CGM system.
