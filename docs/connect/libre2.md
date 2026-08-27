# Libre 2 and Libre 2 Plus EU

Direct Libre Bluetooth support is for the European Libre 2 and Libre 2 Plus variants recognised by the app.

The NFC scan reads the sensor information needed for the Bluetooth connection. After that scan, xDrip4iOS receives readings directly from the sensor.

## Before you connect

- Select Master mode.
- Enable Bluetooth and NFC on the iPhone.
- Start the sensor using the method required for your sensor.
- Disable Bluetooth permission for the Libre app in the iPhone settings.
- Keep any sensor-specific instructions supplied by Abbott available.

Bluetooth permission for the Libre app must remain disabled. Otherwise, it can take over the sensor connection and stop xDrip4iOS from receiving readings.

Regional Libre products are not interchangeable. A Libre 2 sensor from another market can use a different connection method. Choosing the EU option does not make another regional version compatible.

## Scan and connect

In **Devices**, add a `Libre 2/2+ EU` CGM and select **Connect**. Hold the top of the iPhone against the sensor until xDrip4iOS confirms the NFC scan. Then wait for the first reading.

The NFC scan supplies information needed for the Bluetooth connection. Repeat the scan only when xDrip4iOS reports that it is required or that the previous scan failed.

Keep the iPhone still during the scan. If the scan fails, move the top edge of the iPhone slowly around the sensor and use **Scan Again**. A successful NFC scan can still be followed by a short wait for the next Bluetooth reading.

## Using a sensor that is already running

You can connect xDrip4iOS to a supported Libre sensor that has already been started. The NFC scan reads the current sensor information. xDrip4iOS then uses the detected start time and does not restart the sensor or its warm-up.

Keep Bluetooth permission disabled for the Libre app after the scan. The Libre app and xDrip4iOS cannot both control the direct Bluetooth connection.

## Using CamAPS

xDrip4iOS cannot receive direct readings from the same Libre 2 or Libre 2 Plus sensor while CamAPS is using it. CamAPS needs the sensor connection and it cannot be shared with xDrip4iOS.

Do not disable Bluetooth permission for CamAPS or scan the sensor into xDrip4iOS to try to use both apps. This limitation is caused by the way the Libre sensor connects to the iPhone. It is not an xDrip4iOS fault or a missing setting.

See [Using xDrip4iOS with CamAPS](camAPS.md) for the differences between Libre and Dexcom sensors.

## Sensor detection and duration

xDrip4iOS can detect a new Libre sensor and its age. It distinguishes supported Libre 2 Plus variants and uses the detected lifetime when available. Manual start remains available for recovery situations, but normal direct operation should use the sensor information received by the app.

Open the sensor in **Devices** to see its serial number and detected start time. Select **Read Success** to review the percentage of expected readings received during the last 24 hours.

## Calibration options

Compatible devices can show **Algorithm Type** and **Calibration Type** on their screen in **Devices**. Read [Sensor Management](../use/sensor.md) before changing these options.

- **Native Algorithm** uses the sensor calculation supported by xDrip4iOS.
- **xDrip Algorithm** calculates the displayed glucose in xDrip4iOS and requires calibration.
- **Standard** uses the normal xDrip calibration method.
- **Multi-point** uses several previous calibrations and is intended for experienced users.

Changing the algorithm does not repair an NFC or Bluetooth connection. If the sensor is connected but values are doubtful, compare them with an approved meter before changing the calculation method.

## If readings stop

Confirm that Bluetooth is enabled, xDrip4iOS still has Bluetooth permission, and the Libre app still has Bluetooth permission disabled. Check the sensor state in **Devices** and wait for one normal reading interval.

Repeat the NFC scan only when xDrip4iOS asks for it. Repeated scanning does not improve a working Bluetooth connection.
