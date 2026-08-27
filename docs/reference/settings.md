# Settings reference

The settings shown by xDrip4iOS depend on Master or Follower mode, enabled services, and device capabilities.

## Data Source

| Setting | Purpose |
| --- | --- |
| Master or Follower | Selects direct CGM or online download mode |
| Pump & Treatments | Selects Automatic, Nightscout, CareLink, or None when those choices are available |
| Keep-alive | Selects Disabled, Normal, Aggressive, Continuous, or Heartbeat |
| Upload to Nightscout | Sends Master or eligible Follower readings to the configured site |
| Data Source | Selects Nightscout, Dexcom Share, Shared Calendar, CareLink, LibreLinkUp, LibreLinkUp Russia, or Medtrum EasyView |
| Status | Opens the settings and connection information for the selected follower service |

### Follower service screens

- **Nightscout** shows connection and server availability.
- **Dexcom Share** shows Account, Connection, Profile, Activity, and Service.
- **LibreLinkUp** shows Account, Connection, Profile, Sensor, and Service.
- **Shared Calendar** shows Calendar, Connection, Latest Data, and Historical Readings.
- **CareLink** shows Account, Connection, Profile, Therapy Display, Device, and Activity. **Automatic Basal** under Therapy Display selects Basal Pulses or Temp Basals for the main chart.
- **Medtrum EasyView** shows Account, Connection, Profile, and Activity.

Account-based screens provide **Log In**. Some services require account details to be entered in xDrip4iOS first. CareLink opens Medtronic's login page, and its saved username and password are optional. **Log Out** appears at the top of the screen when an account is connected. CareLink and Shared Calendar also provide **Refresh**.

## Glucose Display

**Blood Glucose Units** selects mg/dL or mmol/L for display and entry. Set this before entering glucose ranges, alarm values, calibrations, or blood glucose treatments.

### Home Screen

- allow screen rotation
- show clock when locked
- screen-lock dimming type
- show mini chart
- automatically reset the main chart to the current time
- show original glucose readings when Glucose Adjustments are active
- show sensor noise on the main chart
- select 3, 5, 8, 12, or 24 hours for the main chart
- show remaining sensor lifetime instead of elapsed time.

### Glucose Ranges

- urgent high
- high
- target
- low
- urgent low.

### Statistics

- show compact statistics on **Home**
- time-in-range calculation type
- IFCC A1C unit selection.

## Alerts and Notifications

### Notifications

- show readings in notifications
- notification interval
- Live Activity type
- preview of the selected Live Activity layout
- CarPlay style and preview on iOS 26 or later when a Live Activity is enabled
- show reading in the app badge
- multiply the badge value by ten when required for mmol/L display.

The CarPlay **Style** choices are **Chart** and **Basic**. **Chart** is the default and includes a recent glucose chart. **Basic** shows a larger glucose value without the chart. The same compact layout can also be used by the Apple Watch Smart Stack.

### Alarms

- Alarm Types
- scheduled alarms
- use the Large Snooze Screen when an active alarm opens the snooze picker
- Not Looping alarm when compatible Nightscout AID status is available
- Sensor/Transmitter Failure alarm
- optional Sensor Health Warnings
- xDrip4iOS volume test
- iOS notification volume test.

## Sharing and Services

### Nightscout

- enabled
- open site
- follow type
- URL
- API key or secret
- token
- port
- connection test
- upload sensor start time
- upload schedule.

### Dexcom Share

- enabled
- account name and password
- upload serial number
- US service selection
- upload schedule.

### Calendar Share

- enabled
- shared calendar
- alias sent to follower users
- share status, last value, and timestamp
- recent reading history
- calendar event title and interval.

### Other services

- Write to Apple Health
- Contact Image content and contrast
- OS-AID share type and delay schedule
- warnings for smoothed data shared with OS-AID
- OS-AID sharing disabled for the direct Medtrum Nano Pump source
- warned opt-in sharing for Medtrum EasyView follower readings
- spoken reading language, trend, delta, and interval
- M5Stack colour, Wi-Fi, and Bluetooth settings.

## About xDrip4iOS

Version, build, installation date, licence information, and GitHub project.

## Data Management

- Storage Info
- Create Backup
- Restore Backup
- Import Data
- Manage Data.

**Create Backup** can include app settings and alarms, glucose readings, and treatments. Nightscout AID history and profiles are included when glucose readings or treatments are selected. Account details can be included only in an encrypted backup.

**Restore Backup** can keep current data, fill gaps, replace the backup period, or ignore historical data. Settings, alarms, and selected account details can be restored separately when they are present in the backup.

**Import Data** can import glucose readings, treatments, and Device Status from the configured Nightscout site. Device Status supplies historical AID information for Looping statistics and reports. The available import period is limited by the selected data-retention period.

**Manage Data** controls automatic retention and permanent deletion of selected local history, including Device Status.

## Troubleshooting

**Activity Log** opens a consumer-readable history from up to the previous 24 hours. It shows useful events, failures, and recoveries. The on-screen list can be searched. The toolbar copies or shares the complete report with additional app and configuration context. See [Activity Log](../troubleshoot/activityLog.md).

## Advanced Settings

Advanced settings can include Issue Report, support logging, sensor unlock data, LibreLinkUp version, maximum carbohydrate hours, StandBy display, frequent Nightscout or Apple Health readings, and online-help translation. Change an advanced setting only when its feature guide or a support instruction tells you to do so.
