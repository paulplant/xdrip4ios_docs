# Dexcom Share follower

Dexcom Share follower mode downloads readings from a Dexcom Share account that can follow the sensor user.

The sensor user's official Dexcom app must upload readings to Dexcom Share. xDrip4iOS cannot receive a newer value than the value available in the Dexcom Share service.

## Before you configure it

- Confirm that the sensor user has enabled sharing in the official Dexcom system.
- Confirm that the account used by xDrip4iOS can see the sensor user and a current reading.
- Keep the account name and password available.

## Configure

First confirm that sharing works in the official Dexcom system. Under **Settings > Data Source**, select **Follower**, then select `Dexcom Share` from **Data Source**. Select **Status** to open the Dexcom Share settings.

Enter the account name and password in **Account**, then select **Log In**. The **Connection** section shows the login state. The detected service region and optional alias appear in **Profile**. Confirm that **Home** shows a current reading.

Dexcom uses separate Share services for US and non-US accounts. xDrip4iOS detects the region from the account.

The **Activity** section shows the last connection. The **Service** section shows whether the Dexcom Share service is available. Use **Log Out** at the top of the screen when the account must be disconnected.

The alias is a local name used to identify the person being followed. It does not change the Dexcom account or the sharing name in the official app.

## Background updates

Dexcom Share follower needs internet access and background opportunities from iOS. Start with **Normal** under **Settings > Data Source > Keep-alive**. Try **Aggressive** only if Normal is not reliable enough. Use **Continuous** only in extreme cases because it has the highest battery use.

Do not force-close xDrip4iOS. Always check the reading time because the connection can remain logged in while the source reading is old.

## If login or readings fail

Confirm that the account can still see current readings in the official Dexcom system. Correct the account name or password before trying again. xDrip4iOS can pause repeated login attempts after invalid credentials.

If the connection is logged in but **Home** is old, compare its reading time with Dexcom Share. The sensor user's phone must upload a new reading before xDrip4iOS can download it.

## Share upload conflict

Dexcom Share follower and Dexcom Share upload are different functions. xDrip4iOS disables Share upload when Dexcom Share is selected as the follower source. This prevents the app from sending downloaded readings back to Share.
