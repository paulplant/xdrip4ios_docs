# Dexcom Share

Dexcom Share upload sends readings received by xDrip4iOS to a Dexcom Share account.

This is an upload service. It is different from [Dexcom Share follower](../connect/dexcomShareFollower.md), which downloads readings from an account.

## Before you enable it

Confirm that xDrip4iOS has a current glucose reading. You need the Dexcom Share account name, password, and receiver or upload serial number accepted by the account.

Select the US service only for an account hosted in the United States. Accounts outside the United States use the other service.

## Configure upload

Open **Settings > Sharing and Services > Dexcom Share** and configure:

- upload enabled
- account name
- password
- transmitter or upload serial number
- US or non-US service
- an optional schedule.

The serial number is not the six-character Dexcom G6 transmitter ID and it is not a G7 pairing code. Enter the receiver or upload serial number required by the Dexcom Share account.

After enabling upload, wait for a new reading and confirm that it appears in Dexcom Share with the correct time.

## Upload schedule

Enable **Use Upload Schedule** when readings should be uploaded only during selected times. Open **Schedule** and define the active periods.

Outside the schedule, xDrip4iOS continues to receive and store readings locally but does not upload them to Dexcom Share.

## Follower conflict

Dexcom Share upload is disabled when xDrip4iOS uses Dexcom Share as its follower source. Downloading from and uploading to the same Share path is not supported.

## If readings do not appear

Check the account name, password, serial number, and US service selection. Confirm that xDrip4iOS has received a new reading during an active upload period.

An account can accept a login but reject an unsupported serial number or product. Confirm the account and product requirements in the official Dexcom system.

Credentials are stored for app use. Do not include them in a trace file description or screenshot.
