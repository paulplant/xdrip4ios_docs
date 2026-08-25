# Data sources

xDrip4iOS can obtain glucose readings from a direct Bluetooth connection or from an online follower service.

## Direct CGM connection

Select **Master** in **Settings** and add the CGM from the **Devices** tab. Use this path for:

- Dexcom G6 or ONE
- Dexcom G7, ONE+, or Stelo
- Libre 2 or Libre 2 Plus EU
- a Libre sensor with MiaoMiao or a Bubble-family transmitter
- Medtrum Nano Pump.

Start with [Add a direct CGM device](cgm.md).

## Follower connection

Select **Follower** under **Settings > Data Source**, then select Nightscout, Dexcom Share, Shared Calendar, CareLink, LibreLinkUp, LibreLinkUp Russia, or Medtrum EasyView from **Data Source**. Select **Status** to configure the chosen service. Do not add a CGM device in the **Devices** tab for this mode.

Start with [Follower overview](follower.md).

## Optional Bluetooth devices

A [Follower Heartbeat device](followerHeartbeat.md) can help Follower mode check for new readings in the background. An [M5Stack or M5StickC](devices.md) can display readings received by xDrip4iOS. Neither device supplies glucose readings.
