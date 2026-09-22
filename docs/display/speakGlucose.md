# Speak Glucose

xDrip4iOS can speak current glucose information through the iPhone audio system.

Open **Settings > Sharing and Services > Speak Glucose**. Configure:

- **Speak Glucose**, which is the main on or off switch
- the speech language
- whether trend is spoken
- whether delta is spoken
- the speech interval
- an optional daily schedule.

The interval controls how often a reading is spoken. It does not change how often xDrip4iOS receives or stores readings.

## Daily schedule

Enable **Schedule** to speak readings only between **Enable at** and **Disable at**. The schedule repeats every day using the iPhone's local time. It can cross midnight.

The status shows **Active** when speech is currently allowed. **Inactive** means that **Speak Glucose** is on but the current time is outside the schedule. It does not indicate an error.

The schedule does not turn on **Speak Glucose**. If the main switch is off, the saved schedule remains visible but is not used.

## Quick controls

Use **Quick Show/Hide** to enable or disable **Speak Glucose** without returning to Settings. You can also press and hold the xDrip4iOS Home Screen icon and select **Speak Readings** or **Stop Speaking Readings**.

The Shortcuts app provides **Enable Speak Readings** and **Disable Speak Readings** actions. They change only the main switch and keep the schedule and other speech settings. They affect subsequent readings and do not immediately speak the current value. See [Siri, Shortcuts, and quick actions](shortcuts.md).

The selected speech language is independent of the documentation language. Test pronunciation and units after changing the glucose unit or language.

Speech uses the current audio route. It can play through headphones, a vehicle, a speaker, or another connected device. Consider privacy before enabling it in public or shared environments.

If nothing is heard, confirm that **Home** has a current reading, check that the schedule status is **Active**, check the selected interval, and review the current iPhone audio route and volume.
