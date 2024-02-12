# UniFi Protect Motion / Smart Detection Notifications

This blueprint will send push notifications to a Home Assistant mobile app when a camera detections motion or a
smart detection.

[![Add Blueprint to your HA](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fjrbconsulting%2FHome-Assistant%2Fmain%2FBlueprints%2Fautomation%2Funifiprotect%2Fnotification_smart_motion_event.yaml)

## Required Settings

- UniFi Protect Smart Detection enabled camera or sensor

## Optional Settings

- Notification target for the [mobile app notification target](https://companion.home-assistant.io/docs/notifications/notifications-basic#sending-notifications-to-multiple-devices).
- Time formatting strings. Timestamp is injected into the notification in case the notification is delay.
- Cooldown before sending another notification
- Silence timer for muting notifications via Actionable Notification (docs: [Mobile](https://companion.home-assistant.io/docs/notifications/actionable-notifications/))
- Configurable lovelace view from notification
- Ability to change the color of the notification

## Requirements

To take full effect of this automation blueprint, your Home Assistant instance needs some setup beforehand.

- An UniFi Protect camera that has smart detections enabled. Only cameras that are capable of smart detections (G4, AI or G5 Series cameras) will have smart detection sensors.
- You will need to configure the 'Motion Zones', 'Smart Detection Zones', and/or 'Crossing Lines' in Unifi Protect controller in order for the smart detections to trigger.
- A valid HTTPS certificate and [properly configured external URL](https://www.home-assistant.io/docs/configuration/remote/)
- If you are using Home Assistant Cloud, this is already set up for you.
- If this is not setup correctly, the actionable notifications and attachments will not appear in the notifications.
- You do not need your _whole_ Home Assistant to be publicly accessible. Only the paths `/api/unifiprotect/*` and `/api/webhook/*` need to be accessible outside of your network.
- Highly recommend the use of a tunnel like Cloudflare tunnels to secure your HA remote access.

## Credits

This Blueprint has been modified and had a few changes from the original AngellusMortis/notification_smart_motion_event blueprint.
Please give his blueprint some love as it is absolutely brilliant!

* [UniFi Protect HA Integration](https://www.home-assistant.io/integrations/unifiprotect/) 
* [AngellusMortis Blueprint](https://community.home-assistant.io/t/unifi-protect-blueprints/362604)