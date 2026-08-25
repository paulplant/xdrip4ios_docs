# Supported systems

xDrip4iOS supports the systems listed below. Regional sensor revisions and manufacturer changes can affect compatibility.

## Direct CGM devices

| App choice | Supported family | Important requirement |
| --- | --- | --- |
| Dexcom G6/ONE | Dexcom G6, ONE, and compatible Anubis G6 transmitters | A six-character transmitter ID. The Dexcom app must not use the primary connection at the same time |
| Dexcom G7/ONE+/Stelo | Dexcom G7, ONE+, and Stelo | The Dexcom G7 app must remain running and receive readings |
| Libre 2/2+ EU | European Libre 2 and Libre 2 Plus variants recognised by the app | NFC scan and Bluetooth permission disabled for the Libre app |
| MiaoMiao | Libre sensors supported by the attached MiaoMiao transmitter | Charged transmitter attached to the sensor |
| Nano/Bubble/Bubble Mini | Libre sensors supported by the attached transmitter | Charged transmitter attached to the sensor |
| Medtrum Nano Pump | Medtrum TouchCare Nano CGM relayed by the pump | EasyPatch must remain active in the background and receive readings |

!!! info
    Dexcom G5 remains fully supported internally. It has been removed from the user-facing data source list and general documentation because it is now very obsolete. Existing users can continue to use it.

### Important connection differences

- Dexcom G6 and ONE can use **Primary** or **Coexistence** connection mode. Coexistence is intended for use with the official Dexcom app.
- Compatible Anubis G6 transmitters are recognised automatically and can provide additional transmitter information, a shorter warm-up, extended transmitter life, and transmitter reset controls.
- Dexcom G7, ONE+, and Stelo readings are relayed by the official Dexcom app. That app must remain running and receiving readings.
- Libre 2 and Libre 2 Plus EU connect after an NFC scan. Bluetooth permission for the Libre app must remain disabled.
- MiaoMiao, Bubble, and Nano devices are separate rechargeable transmitters attached to a compatible Libre sensor.
- Medtrum Nano Pump is the Medtrum patch pump connection. It is not a separate CGM named Nano. The EasyPatch app must remain running and receiving readings.

A sensor that is already running can normally be added without restarting it. Follow the device guide and keep the existing session active.

## Follower sources

- Nightscout
- LibreLinkUp
- LibreLinkUp Russia
- Dexcom Share
- Shared Calendar
- CareLink
- Medtrum EasyView

Shared Calendar can receive Calendar Share readings from any release of the app, including xDrip4iOS and Zukka. The source and follower can use different releases.

Follower sources need internet access and a source account, site, or calendar that already contains current readings. They do not connect to the physical sensor on the follower iPhone.

## Follower Heartbeat devices

The app can use a Libre/Generic, Dexcom G7/ONE+/Stelo, or OmniPod device as a background heartbeat. A heartbeat device does not provide glucose data to xDrip4iOS. It only helps Follower mode check for new readings in the background.

The heartbeat device is optional and separate from the selected follower source. It must be added in the **Devices** tab and selected under **Settings > Data Source > Keep-alive**.

## Not available as direct CGM choices

xDrip4iOS does not provide direct CGM choices for Dexcom G4, Libre 3, Medtronic, Eversense, or GlucoMen systems. Some of these systems can still be usable indirectly if their readings are uploaded to a supported follower service.

!!! note
    "Not available as a direct choice" is different from "cannot be viewed." Check whether the system can publish readings to Nightscout, LibreLinkUp, Dexcom Share, Shared Calendar, CareLink, or Medtrum EasyView.
