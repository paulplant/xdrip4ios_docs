# Dexcom Share

Dexcom Share upload sends readings received by xDrip4iOS to a Dexcom Share account.

This is an upload service. It is different from [Dexcom Share follower](../connect/dexcomShareFollower.md), which downloads readings from an account.

## Before you enable it

Confirm that xDrip4iOS has a current glucose reading. You need the Dexcom Share account name, password, and receiver or upload serial number accepted by the account.

Select the US service only for an account hosted in the United States. Accounts outside the United States use the other service.

## Configure upload

Open **Settings > Sharing and Services > Dexcom Share**. Enable **Dexcom Share Upload**, then complete these sections:

- **Account** contains the account name and password.
- **Connection** contains the server region, receiver serial number, current status, and **Test Connection**.
- **Activity** shows the last successful connection, the last successful upload, and any current account or upload error.
- **Options** contains the optional upload schedule.

The serial number is not the six-character Dexcom G6 transmitter ID and it is not a G7 pairing code. Enter the receiver or upload serial number required by the Dexcom Share account.

Select **Test Connection** after entering the account details. This confirms that xDrip4iOS can sign in. The receiver serial number is checked when a reading is uploaded.

After enabling upload, wait for a new reading. Confirm that **Last successful upload** changes and that the reading appears in Dexcom Share with the correct time.

## Upload schedule

Enable **Use Upload Schedule** when readings should be uploaded only during selected times. Open **Schedule** and define the active periods.

Outside the schedule, xDrip4iOS continues to receive and store readings locally but does not upload them to Dexcom Share.

## Follower conflict

Dexcom Share upload is disabled when xDrip4iOS uses Dexcom Share as its follower source. Downloading from and uploading to the same Share path is not supported.

## If readings do not appear

Check the status in **Connection** and the messages in **Activity**. **Not checked** means that the account has not yet been tested. **Paused by schedule** means that the current time is outside the upload schedule.

If the screen asks for configuration, enter the account name, password, and receiver serial number. If it says that the receiver is not assigned to the account, register that receiver through the official Dexcom app.

Confirm that xDrip4iOS has received a new reading during an active upload period. **Last successful connection** can be current even when **Last successful upload** has not changed, so check both values.

An account can accept a login but reject an unsupported serial number or product. Confirm the account and product requirements in the official Dexcom system.

Credentials are stored for app use. Do not include them in a trace file description or screenshot.
