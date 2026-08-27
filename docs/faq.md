# Frequently asked questions

## Can Apple Watch connect directly to my CGM without the iPhone?

No. The xDrip4iOS Watch app displays data supplied by the paired iPhone app. The iPhone remains the Master or Follower data source.

## Why does TestFlight say that the build will expire?

All TestFlight builds expire after Apple's displayed test period. The publisher must upload a newer build. Enable TestFlight automatic updates and contact the publisher before expiry.

## Can I use Libre 3 directly by Bluetooth?

Libre 3 is not a direct CGM choice in xDrip4iOS. It can be viewed through a supported follower path, such as LibreLinkUp, when the official system uploads its readings.

## Can I use xDrip4iOS with CamAPS?

Yes, when CamAPS uses a supported Dexcom sensor. CamAPS controls the sensor connection and must remain running in the background. Use **Coexistence Mode** for Dexcom G6. Dexcom G7 uses the active connection maintained by CamAPS without a separate Coexistence Mode setting.

No, when CamAPS uses Libre 2, Libre 2 Plus, Libre 3, or Libre 3 Plus. The Libre sensor connection used by CamAPS cannot also provide direct readings to xDrip4iOS. This is caused by the way the sensor connects to the iPhone. It is not a fault in either app. See [Using xDrip4iOS with CamAPS](connect/camAPS.md).

## Is Dexcom G5 still supported?

Yes. Dexcom G5 remains fully supported internally. It has been removed from the user-facing data source list and general documentation because it is now very obsolete. Existing users can continue to use it.

## Can I add a Dexcom G6 sensor that is already running?

Yes. Add the transmitter and leave the sensor code field showing its placeholder. Select **OK**. xDrip4iOS reads the existing sensor session from the transmitter and does not start a new session or restart the warm-up.

## Can xDrip4iOS scan a Dexcom G6 sensor code?

Yes. When starting a new G6 sensor, select **Scan with Camera** or **Choose Photo** on the sensor code screen. xDrip4iOS fills in the four-digit code and can save the lot number and sensor serial number from the label. Label scanning is optional and is not needed when the sensor session is already running.

## Can xDrip4iOS and the Dexcom app both receive G6 readings?

Yes. Enable **Coexistence Mode** when the Dexcom app or CamAPS controls the transmitter connection, and keep that app running in the background. If xDrip4iOS connects directly, disable **Coexistence Mode** and normally use the `Mobile App (Default)` Bluetooth channel. Experimental channels are available for specific multi-device setups. See [Dexcom G6 and ONE](connect/dexcomG5G6One.md).

## Why must the sensor app remain open for G7, ONE+, or Stelo?

The app that paired the sensor controls its connection. This is normally the official Dexcom app, but it can be CamAPS for a supported Dexcom G7 sensor. xDrip4iOS receives readings from that active connection. Start and pair the sensor in the controlling app, then leave that app running in the background.

## What is a Follower Heartbeat device?

It is a Bluetooth device that helps xDrip4iOS check an online follower source in the background. It does not send glucose readings to xDrip4iOS. The glucose still comes from Nightscout, LibreLinkUp, Dexcom Share, Shared Calendar, CareLink, or Medtrum EasyView.

## Can I connect a Medtronic, Eversense, GlucoMen, or Dexcom G4 directly?

No direct choice for these systems exists in xDrip4iOS. A system can still be viewable through a supported follower service. Supported Medtronic readings can be received through CareLink when they are available to the CareLink account.

## Why is the widget or Watch value older than Home?

Widgets and Apple Watch update separately from the main app. Open xDrip4iOS and confirm that **Home** has a current value. Compare the reading time shown on the widget or Watch.

## Can I calibrate every sensor?

No. The calibration control appears only when the current CGM supports user calibration. Factory-calibrated systems can hide or reject it.

## How can I create a report for my healthcare professional?

Open **Statistics** and select **Generate Report** at the top of the screen. Select the report period, paper size, language, and optional password, then generate the PDF. See [Statistics](use/statistics.md).

## Does deleting a Bluetooth device stop the physical sensor?

No. It only removes the Bluetooth device from xDrip4iOS. Use **Sensor** or the manufacturer's app to start or stop a sensor.

## How do I move my settings and history to another device?

Open **Settings**, scroll to **Data Management**, and select **Create Backup**. Include the required settings, readings, and treatments. Enable encryption if the backup should include account details. Save the backup file, then open it on the new iPhone or iPad, or use **Restore Backup**. See [Data Management](use/dataManagement.md) before selecting the restore options.

## Is xDrip4iOS a medical device?

No. It is an open-source project and does not replace the approved CGM display, an approved meter, manufacturer instructions, or professional medical advice.
