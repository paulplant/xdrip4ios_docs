# Medtrum Nano Pump

xDrip4iOS connects to the Medtrum Nano Pump, which relays readings from the Medtrum TouchCare Nano CGM.

## Before you connect

The Medtrum EasyPatch app controls the connection to the pump. Keep EasyPatch running in the background and confirm that it is receiving current CGM readings. xDrip4iOS cannot receive new readings when EasyPatch is not receiving them.

Do not force-close EasyPatch after xDrip4iOS connects. Both apps depend on the connection maintained by the Medtrum system.

## Connect

Confirm that EasyPatch is connected to the pump and receiving readings. Select Master mode. In **Devices**, add a `Medtrum Nano Pump` CGM and select **Connect**. Keep the iPhone near the pump until a glucose reading arrives.

Manual sensor start and stop are not offered for this direct source. Manage the physical sensor session through the Medtrum system.

If the CGM session is already running, xDrip4iOS detects its start from the readings relayed by the pump. Adding the pump does not restart the sensor or change its session.

## Device information

Select the Medtrum Nano Pump in **Devices** to check its connection and firmware information. **Read Success** shows how many of the expected readings arrived during the last 24 hours and which hours contain gaps.

The connection shown in xDrip4iOS does not replace the EasyPatch status. EasyPatch must also remain connected to the pump and receive current readings.

## OS-AID sharing

Glucose received directly through the Medtrum Nano Pump cannot be shared with an OS-AID app. **OS-AID Share** is shown as Disabled while this is the direct CGM source.

This does not affect normal glucose display in xDrip4iOS or optional uploads to other supported services.

## If readings stop

First open EasyPatch and check whether it has a current reading and an active pump connection. xDrip4iOS cannot recover data that EasyPatch is not receiving.

If EasyPatch is current, open the Medtrum Nano Pump in **Devices** and check its connection. Keep both apps in the background after reviewing them. Do not delete the device for a short gap.

For cloud-based access to a Medtrum account instead, use [Medtrum EasyView follower](medtrumEasyView.md).
