# Supported systems

xDrip4iOS supports the systems listed below. Regional sensor revisions and manufacturer changes can affect compatibility.

## Direct CGM devices

| App choice | Supported family | Important requirement |
| --- | --- | --- |
| Dexcom G6/ONE | Dexcom G6, ONE, and compatible Anubis G6 transmitters | A six-character transmitter ID. Use Coexistence Mode or separate Bluetooth channels when another app or device also connects |
| Dexcom G7/ONE+/Stelo | Dexcom G7, ONE+, and Stelo | The app controlling the sensor, such as Dexcom or CamAPS, must remain running and receive readings |
| Libre 2/2+ EU | European Libre 2 and Libre 2 Plus variants recognised by the app | NFC scan and Bluetooth permission disabled for the Libre app |
| MiaoMiao | Libre sensors supported by the attached MiaoMiao transmitter | Charged transmitter attached to the sensor |
| Nano/Bubble/Bubble Mini | Libre sensors supported by the attached transmitter | Charged transmitter attached to the sensor |
| Medtrum Nano Pump | Medtrum TouchCare Nano CGM relayed by the pump | EasyPatch must remain active in the background and receive readings |

!!! info
    Dexcom G5 remains fully supported internally. It has been removed from the user-facing data source list and general documentation because it is now very obsolete. Existing users can continue to use it.

### Important connection differences

- Dexcom G6 and ONE can use **Primary mode** or **Coexistence Mode**. Coexistence is intended for use with the official Dexcom app or CamAPS.
- In Primary mode, **Bluetooth Channel** normally uses `Mobile App (Default)`. The experimental `Receiver or Pump` choice leaves the Mobile App channel available for another phone app but can prevent a receiver or pump from connecting.
- Compatible Anubis G6 transmitters are recognised automatically and can provide additional transmitter information, a shorter warm-up, extended transmitter life, transmitter reset controls, and an experimental third Bluetooth channel.
- Dexcom G7, ONE+, and Stelo readings are received through the app that controls the sensor connection. This is normally the official Dexcom app. It can also be CamAPS for a supported Dexcom G7 sensor. The controlling app must remain running and receiving readings.
- Libre 2 and Libre 2 Plus EU connect after an NFC scan. Bluetooth permission for the Libre app must remain disabled.
- MiaoMiao, Bubble, and Nano devices are separate rechargeable transmitters attached to a compatible Libre sensor.
- Medtrum Nano Pump is the Medtrum patch pump connection. It is not a separate CGM named Nano. The EasyPatch app must remain running and receiving readings.

A sensor that is already running can normally be added without restarting it. Follow the device guide and keep the existing session active.

### CamAPS

xDrip4iOS can work alongside CamAPS when CamAPS uses a supported Dexcom sensor. It cannot receive direct readings from a Libre 2 or Libre 3 sensor while CamAPS is using that sensor. This is a difference in how the sensors connect to the iPhone, not a fault in either app. See [Using xDrip4iOS with CamAPS](../connect/camAPS.md).

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
