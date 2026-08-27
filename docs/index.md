# xDrip4iOS user guide

xDrip4iOS displays glucose readings from a supported continuous glucose monitoring system on an iPhone or iPad. It can connect directly to supported Bluetooth devices or receive readings from a supported follower source.

!!! warning "Important safety information"
    xDrip4iOS is an open-source project. It is not a medical device and it does not replace the instructions supplied by your sensor, transmitter, insulin pump, or healthcare professional. Do not make treatment decisions from a value that is missing, delayed, inconsistent with your symptoms, or otherwise doubtful. Check the value with an approved blood glucose meter if needed.

## Find the correct starting point

- If you recently installed the app, follow [First-time setup](getting-started/firstSetup.md).
- If this device receives readings directly from a sensor or transmitter, use [Direct CGM connection](connect/cgm.md).
- If this device downloads another person's readings, use [Follower mode](connect/follower.md).
- If you use CamAPS, check [Using xDrip4iOS with CamAPS](connect/camAPS.md) before adding the sensor.
- For help with a main app screen, open the matching guide: [Home](use/home.md), [Treatments](use/treatments.md), [Statistics](use/statistics.md), [Devices](use/devices.md), or [Settings](use/settings.md).
- For the adaptive tablet layout, see [iPad use](use/ipad.md).
- To back up, restore, import, or remove local data, use [Data Management](use/dataManagement.md).
- If readings have stopped, use [No readings or disconnections](troubleshoot/connectionProblems.md).

## How xDrip4iOS works

In **Master** mode, xDrip4iOS receives glucose data from a locally configured CGM device. In **Follower** mode, it receives glucose data from Nightscout, Dexcom Share, Shared Calendar, CareLink, LibreLinkUp, or Medtrum EasyView. Both modes can show the current value, trend, chart, alerts, treatments, statistics, widgets, and Apple Watch data. Some functions depend on the selected data source.

The app stores its settings and glucose history locally on the device. **Data Management** can create an encrypted backup, restore a backup, import Nightscout history, and control how long local history is kept. Optional services, such as Nightscout, Dexcom Share upload, and Apple Health, remain disabled until you configure them.

## Supported systems

The current direct-connection choices are:

- Dexcom G6 and ONE
- Dexcom G7, ONE+, and Stelo
- FreeStyle Libre 2 and Libre 2 Plus sensors from the European market
- Libre sensors used with a MiaoMiao, Bubble, Nano, or Bubble Mini transmitter
- Medtrum Nano Pump, which relays readings from the Medtrum TouchCare Nano CGM. The EasyPatch app must remain running in the background and receiving readings

See [Supported systems](reference/supportedSystems.md) before buying or configuring hardware. Support for a manufacturer or product family does not mean that every regional version is compatible.

## Get help

Use the [Troubleshooting index](troubleshoot/index.md) first. If the problem continues, collect the details described in [Report a problem](troubleshoot/reportingIssues.md). Never publish passwords, API secrets, tokens, or personally identifying health information in a public issue.
