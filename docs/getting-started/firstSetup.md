# First-time setup

## Select the glucose unit

Under **Settings > General**, select the glucose unit used by you and your care team. Do this before configuring ranges or alerts.

## Select Master or Follower

Open **Settings** and choose one mode:

- **Master** connects to supported CGM hardware through the **Devices** tab.
- **Follower** receives readings from an online account, Nightscout site, or shared calendar.

Changing from Master to Follower removes the active direct CGM and ends its sensor session in xDrip4iOS. The app asks for confirmation when required. Dexcom Share upload is also disabled if it would conflict with Dexcom Share follower mode.

## Configure the source

For Master mode, continue with [Add a direct CGM device](../connect/cgm.md).

For Follower mode, select the required service from **Data Source**, then select **Status** to configure it. Continue with the [Follower overview](../connect/follower.md).

## Confirm the first reading

Return to **Home** and confirm that:

- The glucose value is plausible.
- The reading timestamp is current.
- The data source section at the bottom of the **Home** screen does not show an error.

Wait for the normal reading interval of your system. Do not repeatedly delete and add a device while it is connecting.

## Configure safety-related options

Review these settings:

- glucose ranges
- Alarm Types and alarm schedules
- notification display
- **Keep-alive** under **Settings > Data Source**, if you use Follower mode
- any Nightscout, Dexcom Share, Apple Health, or AID integration.

Test alert sounds at a safe time. iOS volume, Focus modes, notification permission, and the mute switch can affect what you hear.

After setup is complete, open **Settings**, scroll to **Data Management**, and select **Create Backup**.
