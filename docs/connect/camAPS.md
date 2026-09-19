# Using xDrip4iOS with CamAPS

xDrip4iOS can work alongside CamAPS when CamAPS uses a supported Dexcom sensor. It cannot receive readings directly from a Libre 2 or Libre 3 sensor that is being used by CamAPS.

| Sensor used by CamAPS | Can xDrip4iOS receive the same readings? | Connection in xDrip4iOS |
| --- | --- | --- |
| Dexcom G6 | Yes | Add `Dexcom G6/ONE` in **Coexistence Mode** |
| Dexcom G7 | Yes | Add `Dexcom G7/ONE+/Stelo` in **Coexistence Mode** |
| Libre 2 or Libre 2 Plus | No | There is no supported direct connection while CamAPS uses the sensor |
| Libre 3 or Libre 3 Plus | No | Libre 3 is not available as a direct CGM in xDrip4iOS |

CamAPS support for each sensor can depend on the country and the version of CamAPS. The connection rules above apply when the named sensor is supported by your CamAPS system. Check the [CamAPS compatibility information](https://camdiab.com/faq) for current availability.

## Why the sensor makes a difference

CamAPS and xDrip4iOS do not send readings to each other.

With a supported Dexcom sensor, CamAPS connects to the sensor and keeps that connection working. xDrip4iOS can listen for the readings from the same connection. CamAPS must continue running in the background and receiving current readings.

With Libre 2 and Libre 3 sensors, the Bluetooth connection used by CamAPS cannot also provide direct readings to xDrip4iOS. There is no setting in xDrip4iOS that can change this.

This difference is caused by the way each sensor connects to the iPhone. It is not a fault in xDrip4iOS or CamAPS.

## CamAPS with Dexcom G6

1. Confirm that CamAPS is connected to the Dexcom G6 transmitter and has a current reading.
2. In xDrip4iOS, select **Master** under **Settings > Data Source**.
3. In **Devices**, add a `Dexcom G6/ONE` CGM.
4. Select **Coexistence Mode**.
5. Enter the transmitter ID and connect.
6. Keep CamAPS running in the background.

CamAPS remains responsible for the Dexcom connection. Start, stop, and manage the sensor in CamAPS. **Bluetooth Channel** is not used by xDrip4iOS while **Coexistence Mode** is selected.

!!! important
    Keep CamAPS running in the background after the initial setup. If CamAPS stops receiving readings, xDrip4iOS will also stop receiving them.

See [Dexcom G6 and ONE](dexcomG5G6One.md) for the complete connection guide.

## CamAPS with Dexcom G7

1. Start and pair the sensor in CamAPS.
2. Confirm that CamAPS has a current reading.
3. In xDrip4iOS, select **Master** under **Settings > Data Source**.
4. In **Devices**, add a `Dexcom G7/ONE+/Stelo` CGM.
5. Select **Coexistence Mode**.
6. Leave the Bluetooth name empty and continue to the device screen.
7. Select **Scan** and keep CamAPS running in the background.

CamAPS controls the sensor connection. xDrip4iOS reads from that active connection. **Bluetooth Channel** is not shown because CamAPS controls which channel is used.

Do not select **Primary Mode** for this setup. Primary Mode makes xDrip4iOS control the sensor connection and cannot be used while CamAPS controls the same connection.

See [Dexcom G7, ONE+, and Stelo](dexcomG7OnePlusStelo.md) for the complete connection guide.

## CamAPS with Libre 2 or Libre 3

There is no supported way for xDrip4iOS to receive direct readings from the same Libre 2, Libre 2 Plus, Libre 3, or Libre 3 Plus sensor while CamAPS is using it.

Do not disable Bluetooth permission for CamAPS or try to move the sensor connection to xDrip4iOS. CamAPS needs its glucose connection for the features provided by the CamAPS system.

xDrip4iOS does not currently provide a CamAPS follower source. Libre 3 is not available as a direct CGM choice in xDrip4iOS.

## If Dexcom readings stop in xDrip4iOS

Check CamAPS first. It must be open in the background and show a current reading. If CamAPS is not receiving readings, restore its sensor connection before changing anything in xDrip4iOS.

For Dexcom G6 and G7, confirm that **Coexistence Mode** is selected and that the correct device is shown in **Devices**. Do not delete the device because of a short gap.
