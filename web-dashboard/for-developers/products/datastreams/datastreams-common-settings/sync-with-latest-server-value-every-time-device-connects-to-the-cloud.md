# Sync with latest server value every time device connects to the cloud

Enable this option to set higher priority to the values changes made in Blynk.App or Blynk.360 instead of those sent from a Device. Useful for controlling Devices.

For example, a user owns a wi-fi connected dimmer light

1. The device goes offline
2. User sets the brightness of the light to 100% in the mobile app or on the web
3. When the device comes back online, it can request the latest value from the server and set brightness to 100

To sync the device to the latest state, use the firmware API commands:

Blynk.syncAll\(\) will sync only Datastreams that are enabled for sync \(with this setting\).

BLYNK\_CONNECTED\(\) { // when device is conneceted to Blynk Cloud... Blynk.syncAll\(\); // request the values for all datastreams that has "sync" setting enabled } Blynk.sync\(\) will sync any requested Datastream, even if sync setting is not enabled for the specified datastream

BLYNK\_CONNECTED\(\) { // when device is conneceted to Blynk Cloud... Blynk.sync\(V0\); // syncs V0 pin only \(even if sync setting is off for V0 }

