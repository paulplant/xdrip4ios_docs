# Siri, Shortcuts, and quick actions

xDrip4iOS provides Siri and Shortcuts actions for the latest glucose and Speak Glucose. It also provides a Live Activity restart action and an app-icon quick action for spoken readings.

## Ask for the latest glucose

Use Siri with a phrase such as `What is my glucose in xDrip4iOS?` The action reads the latest stored glucose, describes its trend, and can show a short chart.

If the latest stored reading is more than seven minutes old, the response includes its age. If it is more than thirty minutes old, the response says that no recent glucose value is available.

## Use the Shortcuts app

Find xDrip4iOS actions in Apple's Shortcuts app. The available actions include:

- **What's my glucose level**
- **Enable Speak Readings**
- **Disable Speak Readings**
- **Restart Live Activity**.

The two speech actions change only the **Speak Glucose** main switch. They keep the language, interval, trend, delta, and daily schedule. They affect subsequent readings and do not immediately speak the current glucose value.

These separate enable and disable actions are suitable for personal automations because running the same action again does not reverse the intended state. The daily speech schedule still applies after speech is enabled.

You can use **Restart Live Activity** in a personal automation when iOS regularly ends a Live Activity. Frequent automation does not override iOS background or ActivityKit limits.

## App-icon quick action

Press and hold the xDrip4iOS icon on the Home Screen. The menu offers **Speak Readings** when speech is off and **Stop Speaking Readings** when speech is on.

## Privacy and age

The glucose shortcut is allowed while the device is locked so that Siri can answer. Consider who can hear or request the response. Always check the spoken or displayed reading age.
