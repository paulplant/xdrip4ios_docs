# Activity Log

The Activity Log explains recent xDrip4iOS activity in a form that is easier to read and safer to share than a developer trace file.

Open **Settings**, scroll to **Troubleshooting**, then select **Activity Log**.

The newest information appears first. Entries are grouped by day and the screen updates when new useful information is recorded.

Use the field at the top of the screen to search the visible entries. Enter a word or phrase and press **Search**. Clear the field to show the complete list again.

## What the log can explain

The Activity Log can include:

- app starts and closures
- Bluetooth scanning, connection, disconnection, pairing, and recovery
- the displayed Bluetooth name for some user-initiated device actions
- direct CGM setup, NFC scan results, and Dexcom G6 sensor label scan results
- Follower sign-in, download, failure, retry, and recovery
- accepted glucose readings and calibrations
- sensor sessions, submitted sensor codes, sensor noise, sensor health conditions, and transmitter read success
- alerts that were raised, scheduled, snoozed, dismissed, disabled, or blocked by notification permission
- Nightscout, Apple Health, Apple Watch, Live Activity, Calendar, and OS-AID updates
- changes to data source, keep-alive, therapy source, Dexcom connection mode, Dexcom Bluetooth channel, Live Activity, and glucose processing settings
- completed backup, restore, cleanup, and deletion actions
- changes to glucose readings and treatments.

The log records useful milestones and outcomes. It filters routine polling, normal between-reading Bluetooth connections, repeated healthy results, and repeated copies of the same problem. A recovery entry appears when a previously failing connection or service works again.

New glucose entries show the value stored by xDrip4iOS after Glucose Adjustments and Smoothing. When that visible value differs from the original reading, the original appears in brackets as `orig`. This makes it easier to confirm why xDrip4iOS and the original data source show different values.

This filtering means the Activity Log is not a list of every background action. A missing routine entry does not mean that the app was inactive.

## Understand the time shown

The time at the start of a row is when xDrip4iOS recorded that activity.

Some rows also contain the time assigned to a glucose reading or treatment. These times can differ when xDrip4iOS downloads older information, restores a missing reading, or when you edit historical data.

## How long information is kept

xDrip4iOS keeps up to the previous 24 hours of Activity Log information. Older entries are removed automatically. If an unusually large amount of activity is recorded, the oldest entries can be removed sooner.

Open the Activity Log soon after a problem occurs. Note the local time of the problem before changing the data source, account, Bluetooth device, or other relevant settings.

## Copy or share the log

Use the copy button in the top toolbar to place the complete report on the clipboard. The checkmark confirms that it was copied.

Use the Share button to send or save the same report. xDrip4iOS does not send the Activity Log automatically.

Searching changes only the list shown on the screen. The copied or shared report always contains the complete Activity Log, including entries hidden by the current search. It also adds context that is useful when interpreting the history:

- app version
- iPhone or iPad class and iOS version
- Master or Follower mode and the selected data source
- background keep-alive mode when applicable
- selected Dexcom Bluetooth channel when a Dexcom G6 or ONE transmitter is configured
- glucose units and glucose-processing settings
- the enabled state of supported sharing and display integrations.

This extra context appears only in the copied or shared report. It is not repeated at the top of the Activity Log screen.

!!! warning
    The Activity Log avoids passwords, access tokens, account names, service URLs, Bluetooth addresses, transmitter IDs, free-form notes, treatment amounts, and raw server responses. It can still contain the displayed Bluetooth name, glucose values, timestamps, treatment categories, device types, and other health-related context. Review the report before posting it publicly.

## Activity Log and Issue Report are different

The Activity Log is a short recent history intended to help you understand app behaviour and share useful context in a support conversation.

An **Issue Report** can attach detailed developer trace files. Those files can contain identifiers, service responses, and more private technical information. Use an Issue Report only when an xDrip4iOS developer asks for one.

Opening, copying, or sharing the Activity Log does not attach the developer trace files.

See [How to ask for help](reportingIssues.md) for the other information to include in a useful support request.
