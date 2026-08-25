# LibreLinkUp follower

LibreLinkUp follower mode downloads readings available to an Abbott LibreLinkUp account.

xDrip4iOS does not connect to the sensor in this mode. The sensor user's official Libre app must first receive and upload the reading.

## Before you configure it

- The sensor user's official app must already upload readings to LibreLinkUp.
- The account used by xDrip4iOS must be able to see that user.
- Use `LibreLinkUp Russia` only for an account hosted by that separate service.

## Configure

Under **Settings > Data Source**, select **Follower**, then select `LibreLinkUp` or `LibreLinkUp Russia` from **Data Source**. Select **Status** to open the LibreLinkUp settings.

Enter the account email address and password in **Account**, then select **Log In**. The **Connection** section shows the login state. The detected region and optional alias appear in **Profile**. Confirm that **Home** shows a current reading.

The alias is a local name used to identify the person being followed. It does not change the LibreLinkUp account.

LibreLinkUp might not provide every sensor detail. When available, the **Sensor** section shows the sensor family, serial number, start date, and the 15-day sensor option. Enable the 15-day option when the connected Plus sensor uses that lifetime.

The **Service** section shows whether LibreLinkUp is available. Use **Log Out** at the top of the screen when the account must be disconnected.

If Nightscout upload and **Upload Sensor Start Time** are enabled, xDrip4iOS can also upload the LibreLinkUp sensor start to Nightscout.

## Login protection

After invalid credentials, xDrip4iOS can pause repeated login attempts. Correct the email address or password to allow a new login. Repeated failed logins can trigger restrictions from the service.

Changing the account details clears the previous connection and sensor information so that xDrip4iOS can identify the new account correctly.

## Background updates

LibreLinkUp follower needs internet access and background opportunities from iOS. Start with **Normal** under **Settings > Data Source > Keep-alive**. Try **Aggressive** only if needed. Use **Continuous** only in extreme cases because it has the highest battery use.

Do not force-close xDrip4iOS. If **Home** shows an old reading, compare it with LibreLinkUp. The sensor user's app must upload a new reading before xDrip4iOS can download it.

## 15-day Libre Plus sensors

When sensor information is available, the **Sensor** section identifies the detected Libre family and start date. Enable **Is a Libre Plus?** only when the followed sensor is a 15-day Plus model.

This setting changes the expected sensor lifetime shown by xDrip4iOS. It does not change the sensor or the LibreLinkUp account.
