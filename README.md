This is a clone of the oringinal Renault API and Home Assistant Renault Integration by epinet. I created this as a temporary solution until the original code is updated with the changes included in here. 
This is not intended as a replacement, nor will it act as a replacement when installed on HA. This version has aly be tested for my Renault Megane e-Tech.

The changes included:
Renault API:
- Implemented kamereon/helper:create_charge_schedule to fix issue for charge_set_schedule action when there are no current schedules
- Add optional startDateTime to charge-start function.
- Add KCM endpoints for charge-set-schedule and charge-start for Megane e-Tech as KCA endpoints are failing.
- Add attributes to KamereonVehicleChargingSettingsData class

HA Renault Integration:
- Change domain to renault_megane
- Add charge_start action with optional when parameter to specify a startDateTime
- Add attributes for schedules, startDateTime, delay and dateTime (last update) to Chargin Mode sensor. These attributes are not stored in the HA Database.

To install create the folder renault_megane in homeassistant/custom_components and restart HA. The add integration Renault Megane.

The offical Renault API is found at https://github.com/hacf-fr/renault-api
The office Renault Integration documentation is found at https://www.home-assistant.io/integrations/renault
