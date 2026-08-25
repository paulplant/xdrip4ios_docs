# Follower Heartbeat devices

A heartbeat device can help Follower mode check for new readings while xDrip4iOS is in the background. It does not supply glucose readings.

Bluetooth activity from the selected device gives xDrip4iOS an opportunity to wake and check the configured follower source. The glucose still comes from Nightscout, Dexcom Share, Shared Calendar, CareLink, LibreLinkUp, or Medtrum EasyView.

## Available choices

- `Libre/Generic` uses the Bluetooth activity from a Libre device or another compatible device.
- `Dexcom G7/ONE+/Stelo` uses the Bluetooth activity from that sensor family.
- `OmniPod` uses Bluetooth activity from a compatible OmniPod.

## Configure

Configure Follower mode and its glucose source first. In **Devices**, add a **Follower Heartbeat** device and select its family. Enter an identifier when requested and connect the device. Then select `Heartbeat` from **Keep-alive** under **Settings > Data Source**.

The follower source remains the selected online service or shared calendar. If that source is unavailable, the heartbeat cannot create a glucose reading.

### Libre or Generic

Before adding this heartbeat, force-close the app that normally controls the Bluetooth device. Find the device name under the iPhone Bluetooth settings and enter that name in xDrip4iOS. After the heartbeat connects, reopen the controlling app if it is still needed.

Compatible EmaLink and OrangeLink devices can show their battery level on the device information screen. The battery row appears only when the device provides a supported battery value.

### Dexcom G7, ONE+, or Stelo

Enter the Bluetooth name shown under the iPhone Bluetooth settings. The official Dexcom app must still be configured correctly for the sensor. The heartbeat connection does not replace that app or turn the sensor into a direct xDrip4iOS data source.

### OmniPod

Keep the pod near the iPhone while xDrip4iOS scans. The pod continues to be controlled by its normal system. xDrip4iOS uses only its Bluetooth activity as a heartbeat.

## Check that it is working

Open the heartbeat in **Devices** and confirm that it is active. Then return to **Settings > Data Source** and confirm that **Keep-alive** is set to **Heartbeat**.

The data source section at the bottom of **Home** shows the follower source and background method. Always check the reading time. A connected heartbeat cannot provide a reading when the follower service, calendar sync, or internet connection is unavailable.

## Battery use and limitations

Heartbeat normally has less effect on iPhone battery life than the audio-based keep-alive modes. It depends on regular Bluetooth activity from the selected device and cannot guarantee that iOS will allow every background check.
