# Microsoft Power Automate-tions
Automations I've created in Microsoft Flow/Power Automate

## Flows

1. Copying events over from a predefined time period from Microsoft Shifts to Outlook or Google Calendar (two different flows).

Features:

* Add everyone's shifts or just your shifts
* Custom event name
* Fetches Calendar ID and Teams ID from "friendly" name
* Delete/remove events from your calendar using the name you give the event
* Remove shifts already created as events

With those last two features you get the ability to change the name of your shift event at a later time by removing all the events with the previous shift name and adding shifts again as events with a new name

***I highly recommend creating your own calendar for this in either Outlook or Google Calendar. I am in no way responsible if your events get deleted!***

_Please read over the limitations to ensure you know what this Flow cannot do!_

**Configuration**  
There are multiple parameters for this flow. They are explained here:

| Parameter Name       | Meaning     | Default Value     |
| :------------- | :----------: | -----------: |
|  Event Name | Name for the event in Outlook/Google Calendar   | CRW    |
| Calendar Name  | Friendly calendar name you see in Outlook/Google Calendar | Calendar |
| Microsoft Teams Team Name | Friendly team name you see in Microsoft Teams | og_crw |
| Get everyone's shifts (true) or just my shifts (false) | Choose to get everyone's shifts if true or just your shifts if false  | false |
| Delete calendar events (true) or not (false) | Choose to delete existing calendar events matched to the event name parameter if true or not if false  | true |
| Delete calendar events (true) or not (false) | Choose to delete existing calendar events matched to the event name parameter if true or not if false  | true |
| Remove existing work shift events from calendar (true) or not (false) | If true, won't add new events to the calendar. Can be used to remove all work shift events from calendar (and possibly more so be careful); useful to change the name of your shift event after you've already synced  | false |
| Calendar Time Zone | Necessary for Outlook Calendar but not included for Google Calendar. If you don't know your time zone string, you can add the action Convert To Time Zone to get it. | (UTC-08:00) Pacific Time (US & Canada) |
| Get past time - Begin Date | Set the date in the past to start getting shifts and creating events | 0 Months (now) |
| Get future time - End Date | Set the date in the future to start getting shifts and creating events | 3 Months |

**Limitations**
- [ ] Microsoft Teams actions are currently in preview action and don't support pagination; the maximum amount of shifts you can grab at a time are 100. If you have trouble getting all the shifts you want, you'll need to tweak the begin and end date to a shorter interval. This is especially true if you have a larger team since this flow must iterate through all team member's shifts.
- [ ] No current easy way via Power Automate to copy over the color of the shift to the calendar color. This isn't an option in create an event for Google Calendar or Outlook Calendar
- [ ] Possible timeouts may occur while iterating through the shifts though I haven't personally experienced them

<div style="text-align:center"><a href="https://www.buymeacoffee.com/vyKzl3x" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" style="height: 51px !important;width: 217px !important;" ></a></div>
