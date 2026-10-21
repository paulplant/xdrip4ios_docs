# Libre 3 / 3 Plus

xDrip4iOS can connect directly to a compatible Libre 3 or Libre 3 Plus sensor in Master mode.

!!! warning "Legal and safety notice"
    Libre 3 support is not from Abbott. xDrip4iOS includes independently developed open-source work from [RoundWhiteDiscKit](https://github.com/airedev326/RoundWhiteDiscKit). Both projects are independent. They are not made by, affiliated with, endorsed, sponsored, reviewed, or supported by Abbott Laboratories, Abbott Diabetes Care, or any of their affiliates.

    FreeStyle Libre, Libre, and related names and marks are trademarks of Abbott. They are used here only to identify compatible sensors.

    This feature is experimental. It is not a medical device and has not been approved or cleared by a regulator. Do not use it for treatment or dosing decisions. Confirm readings with approved equipment when necessary and follow the official instructions for your sensor. Do not contact Abbott for support with xDrip4iOS.

## Before you start

You need:

- a compatible Libre 3 or Libre 3 Plus sensor
- an iPhone with NFC
- Bluetooth permission for xDrip4iOS
- internet access before the first NFC scan so xDrip4iOS can download the required connection credentials.

Under **Settings > Data Source**, select **Master**. In **Devices**, select the add button, **CGM**, then **Libre 3 / 3 Plus**.

The setup screen provides three choices. Select the choice that matches the current sensor.

## Start a new sensor

Select **Start a new sensor** only for a sensor that has not been started.

1. Select **Scan Sensor with NFC**.
2. Hold the top of the iPhone near the sensor until the scan finishes.
3. Keep xDrip4iOS open while it completes the setup.

The scan starts the sensor wear period. Bluetooth then connects automatically. Wait for authentication and sensor warm-up to finish.

After setup, open the sensor under **Devices** and select **Receiver ID** to copy it. Keep this eight-character ID somewhere outside xDrip4iOS. It can be required to reconnect the same active sensor after reinstalling the app or moving to another iPhone.

!!! important
    Do not select **Start a new sensor** for a sensor that is already active. Use **Connect using Receiver ID** or **Import from original app** instead.

## Connect using Receiver ID

Use this choice for an active sensor when you know the Receiver ID that originally started it.

1. Select **Connect using Receiver ID**.
2. Enter the exact eight-character Receiver ID.
3. Select **Scan Sensor with NFC** and scan the active sensor.

This changes the sensor connection to xDrip4iOS. It does not restart the wear period or warm-up.

An encrypted xDrip4iOS backup does not contain the information needed to reconnect an active Libre 3 sensor. Keep the Receiver ID separately until the sensor has ended.

## Import from original app

Use this experimental choice when the active sensor was started by an official Libre app and you do not have its Receiver ID.

1. Select **Import from original app**.
2. Under **App used**, select **FreeStyle Libre 3** or **Libre by Abbott**.
3. Enter the Account ID used by the app that started the sensor.
4. If you do not know the Account ID, select **I don't know my Account ID** and sign in with the same account that started the sensor.
5. Stop the original app from using the sensor Bluetooth connection.
6. Select **Scan Sensor with NFC** and scan the active sensor.

Use the sensor user's original account. A follower or caregiver account cannot recover the connection details. xDrip4iOS does not save the password entered on the account lookup screen.

The correct **App used** choice is important because the two official apps create the Receiver ID differently. An NFC scan alone cannot recover an unknown Receiver ID.

## After connecting

The sensor information page can show:

- sensor start and expected expiry
- current sensor status
- sensor serial number and firmware
- the Receiver ID.

xDrip4iOS receives minute readings and can recover available missing readings after a temporary connection gap. It also respects the sensor warm-up, error, expiry, and end states.

When xDrip4iOS controls the direct Bluetooth connection, the original Libre app no longer receives the sensor. Its alarms and uploads to LibreView or LibreLinkUp will not continue through that app. Configure the required alarms and sharing services in xDrip4iOS.

## Libre 3 credentials

xDrip4iOS downloads the required credentials automatically before the first NFC scan. Saved sensor connections can continue without repeating this download.

If the setup screen says that credentials are unavailable, check the internet connection and select **Retry download**. Downloaded versions can be reviewed under **Settings > Advanced Settings > Libre 3 Credentials**. Changing the selected version affects the next NFC setup. It does not change the active sensor.

## CamAPS

xDrip4iOS cannot receive direct readings from the same Libre 3 or Libre 3 Plus sensor while CamAPS is using it. The sensor Bluetooth connection cannot be shared between these apps. This is caused by the way the sensor connects to the iPhone. It is not an xDrip4iOS or CamAPS fault.

Do not remove the CamAPS connection if CamAPS needs that sensor for insulin delivery. See [Using xDrip4iOS with CamAPS](camAPS.md).

## If the sensor does not connect

Confirm that Bluetooth is enabled, xDrip4iOS has Bluetooth permission, and the original app is no longer using the sensor connection. Check that the setup choice and Receiver ID belong to the current sensor.

Do not repeatedly scan an active sensor with **Start a new sensor**. Return to the setup screen and use the correct active-sensor choice.

See [No readings or disconnections](../troubleshoot/connectionProblems.md) for general Bluetooth checks.
