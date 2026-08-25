# Libre with MiaoMiao or Bubble

MiaoMiao and Bubble-family devices read a compatible Libre sensor and relay its data to xDrip4iOS by Bluetooth.

## Supported app choices

- `MiaoMiao`
- `Nano/Bubble/Bubble Mini`

The attached transmitter does not make every Libre regional variant compatible. Compatibility depends on both the sensor and transmitter firmware.

## Connect

Charge the transmitter and attach it to the active Libre sensor. In **Devices**, add the matching CGM family and select **Connect**. Keep the iPhone close until the first complete reading arrives.

The app can detect the attached sensor and its age. A transmitter can take more than one reading cycle to send all required sensor data.

If the sensor session is already running, xDrip4iOS uses the session information supplied by the transmitter. It does not restart the physical sensor.

## Device information

Open the configured device in **Devices** to check the detected sensor type, sensor serial number, sensor status, transmitter battery, firmware, and hardware information. The available details depend on the transmitter and its firmware.

The battery shown is the battery in the MiaoMiao or Bubble device. It is not the sensor battery. Charge the transmitter when its battery is low or when connections become unreliable.

Select **Read Success** to review the percentage of expected readings received during the last 24 hours. Repeated gaps can indicate positioning, battery, distance, or transmitter firmware problems.

## Algorithm and Calibration Type

In the **Devices** tab, select the configured MiaoMiao or Bubble device. Compatible devices show two settings:

- **Algorithm Type** selects **Native Algorithm** or **xDrip Algorithm**.
- **Calibration Type** selects **Standard** or **Multi-point** when the xDrip Algorithm is active.

These settings change how glucose values are calculated. They cannot repair a Bluetooth connection.

!!! warning
    Multi-point calibration is intended for experienced users. An incorrect calibration can produce unsafe values. Compare doubtful readings with an approved meter.

## If it does not connect

Confirm that the transmitter is charged and firmly positioned over the sensor. Keep the iPhone close and wait for more than one reading cycle. Check that the selected app choice matches the transmitter family.

If the device connects but no sensor information appears, check that its firmware supports the attached Libre sensor. A transmitter can connect by Bluetooth even when it cannot read that sensor model.
