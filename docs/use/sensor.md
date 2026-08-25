# Sensor Management

The **Sensor Management** screen shows the active sensor, available sensor actions, and calibration information.

Select the sensor button in the toolbar at the top of **Home**.

## Sensor summary

The summary can show the sensor family, start date, elapsed time, remaining time, expected lifetime, transmitter information, and expiry state. The exact fields depend on the configured device.

Dexcom G7-family sensors and the CGM used by the Medtrum Nano Pump are started and stopped by their own systems. xDrip4iOS does not show manual start or stop controls for them. The available controls for Libre and Dexcom G6/ONE depend on the connected transmitter.

## Start a sensor

If **Start Sensor** is available:

1. Confirm that the physical sensor is inserted and the transmitter is ready.
2. Select **Start Sensor**.
3. Enter the actual start time when requested.
4. Enter the printed sensor code when the transmitter requests one.
5. Confirm the start.

Use only the code printed for the sensor. The transmitter can reject a wrong code or use it to calculate incorrect readings.

For a Dexcom G6 session, leaving the code empty uses `0000` and starts a no-code session. The transmitter will then request regular calibrations. xDrip4iOS shows a warning before this is confirmed.

This applies only when you deliberately select **Start Sensor** and the transmitter has no active session. If a Dexcom sensor session is already running when the transmitter is added, leave the placeholder code unchanged and select **OK**. xDrip4iOS reads the existing session from the transmitter and does not start it again. See [Dexcom G6 and ONE](../connect/dexcomG5G6One.md#connecting-to-a-sensor-session-that-is-already-running).

## Stop a sensor

Select **Stop Sensor** only when you intend to end the current sensor. Stopping a sensor is different from disconnecting or deleting its Bluetooth device.

For Dexcom G7, ONE+, Stelo, and Medtrum Nano Pump, start and stop the sensor in the official app that controls the system. xDrip4iOS follows the session information it receives.

## When calibration is available

The calibration control appears only when the connected CGM accepts a user calibration. Factory-calibrated systems can hide or disable it.

To calibrate:

1. Wash and dry your hands.
2. Use an approved blood glucose meter.
3. Wait until glucose is stable.
4. Open **Sensor** and select **Calibrate**.
5. Enter the meter value in the unit shown by the app.
6. Review any large-difference warning before confirming.

After a valid meter value is entered, the calibration screen checks that value together with the recent trend and sensor noise. Before a valid value is entered, **Calibration Value** shows **Pending...**. The result indicates whether conditions are good, less suitable, or unsuitable for calibration.

This is guidance only. Follow the calibration instructions for the sensor and wait when glucose is changing quickly. A separate warning appears if the entered meter value differs greatly from the current sensor reading.

Open **Calibration Details** to see previous calibrations and their blood glucose value, raw sensor value, slope, and intercept.

!!! warning
    Do not calibrate from another CGM value. Do not calibrate during rapid change unless the sensor manufacturer's procedure explicitly requires it. A poor calibration can affect later readings.

## Algorithm and Calibration Type

Some devices show **Algorithm Type** and **Calibration Type** after you select the device in **Devices**.

- **Native Algorithm** uses the value calculated for the sensor or transmitter.
- **xDrip Algorithm** calculates readings in xDrip4iOS and requires calibration.
- **Standard** uses the normal xDrip calibration method.
- **Multi-point** uses several previous calibrations and is intended for experienced users.

The available choices depend on the connected transmitter. A **Calibrate** button does not mean that calibration is required.

## Sensor Noise

When enough readings are available for an active direct sensor, the **Sensor Noise** section shows the status for the last 30 minutes, the last 4 hours, and the last 12 hours. The possible states are **Collecting data**, **Low**, **Elevated**, **Very High**, and **Extreme**.

Select the **Sensor Noise** row to open **Noise History**. It opens at the widest useful range for the current sensor. Depending on the sensor age, the choices can include 1 day, 3 days, 7 days, or the complete sensor session. Lower noise values mean that the readings changed more smoothly. They do not prove that the readings are accurate.

**Sensor Sensitivity** changes how early the app classifies the signal as noisy:

- **Sensitive** warns earlier.
- **Normal** uses the standard limits.
- **Permissive** allows more variation before warning.

Changing the sensitivity does not change stored glucose or noise values. If a reading is doubtful or does not match symptoms, check it with an approved blood glucose meter.

## Sensor health warnings

xDrip4iOS can show a warning on **Home** when it detects:

- very high sensor noise over a prolonged period
- readings that remain unchanged for 30 minutes
- a temporary sensor issue reported by a supported transmitter
- a sensor failure
- a transmitter failure.

Select the warning to open the relevant Sensor or device screen. The warning can be dismissed after it has been reviewed.

Optional iOS notifications for prolonged noise, an unchanged signal, and temporary sensor issues are controlled by **Sensor Health Warnings** under **Settings > Alerts and Notifications**. Sensor and transmitter failures use the **Sensor/Transmitter Failure** alarm configured with the other alarms.

These warnings do not confirm that a glucose value is accurate or inaccurate. Check a doubtful reading with an approved blood glucose meter and follow the instructions for the sensor.

## Sensor lifetime on Home

The sensor line near the bottom of **Home** normally shows the elapsed sensor time. Open **Settings > Glucose Display > Home Screen** and enable **Prefer Sensor Countdown** to show the estimated time remaining instead. The same choice is used by the Apple Watch app. This option changes the display only. It does not extend or stop the sensor.
