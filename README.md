# Microsoft Power Automate-tions
Automations I've created in Microsoft Flow/Power Automate

## Flows

### Copying shifts from Microsoft Shifts over a predefined time period to Outlook or Google Calendar (two different flows).

**Links:**  
[Shifts to Outlook Calendar](https://github.com/codycodes/microsoft_power_automate/releases/download/1.0/MicrosoftTeamsShifts-OutlookCalendarEvents_20200106003516.zip)  
[Shifts to Google Calendar](https://github.com/codycodes/microsoft_power_automate/releases/download/1.0/MicrosoftTeamsShifts-GoogleCalendarEvents_20200106003403.zip)  

**You can find these flows on the [Releases](https://github.com/codycodes/microsoft_power_automate/releases) page of GitHub as well; if there are updates they will go there!**

**Setup**  
In order to setup these flows, you must download them from above and import them (more info for this can be found [here](https://flow.microsoft.com/en-us/blog/import-export-bap-packages/)) and select the data connections for the following:
* Microsoft Shifts Copy to Outlook Calendar or Microsoft Shifts Copy to Google Calendar -> Ensure this is "Create as new" (found in dropdown under import setup link if not already selected)
* Microsoft Teams Connection -> Select your Microsoft Teams account or set it up as a new connection after clicking "Select during import"
* Office 365 Outlook Connection -> Select your Outlook Connection or set it up as a new connection after clicking "Select during import"
* Office 365 Users Connection -> Select your Users Connection or set it up as a new connection after clicking "Select during import"

**Hint: you can copy this flow after you've created it if you want to have a separate calendar which syncs everyone's shifts in addition to a calendar that syncs just your shifts!**

Requirements:
- [x] Microsoft Power Automate account to use these flows!
- [x] Either a Google or Microsoft account
- [x] Be part of an Office 365 Organization (run the flow and see if it works)

Features:

* Add everyone's shifts or just your shifts
* Custom event name
* Fetches Calendar ID and Teams ID from "friendly" name
* Delete/remove events from your calendar using the name you give the event
* Remove shifts already created as events

With those last two features you get the ability to change the name of your shift event at a later time by removing all the events with the previous shift name and adding shifts again as events with a new name

***I highly recommend creating your own calendar for this (especially a separate calendar for each team member's shifts and your own shifts) in either Outlook or Google Calendar. I am in no way responsible if your events get deleted!***

_Please read over the limitations to ensure you know what this Flow cannot do!_

**Configuration**  
There are multiple parameters for this flow. Some of the default values may be different for the Google Calendar Flow but they mean the same thing. You can dig into the flow and change the location of the event, color, and alerts if you'd like as well (colors and alerts for Google Calendar in the Calendar settings at calendar.google.com)

| Parameter Name       | Meaning     | Default Values (may be different if Google Calendar Flow) |
| :------------- | :----------: | -----------: |
|  Recurrence | Frequency for running Flow automation  | 1 Hour    |
|  Event Name | Name for the event in Outlook/Google Calendar   | CRW    |
| Calendar Name  | Friendly calendar name you see in Outlook/Google Calendar | Calendar |
| Microsoft Teams Team Name | Friendly team name you see in Microsoft Teams | og_crw |
| Get everyone's shifts (true) or just my shifts (false) | Choose to get everyone's shifts if true or just your shifts if false  | false |
| Delete calendar events (true) or not (false) | Choose to delete existing calendar events matched to the event name parameter if true or not if false  | true |
| Remove existing work shift events from calendar (true) or not (false) | If true, won't add new events to the calendar. Can be used to remove all work shift events from calendar (and possibly more so be careful); useful to change the name of your shift event after you've already synced  | false |
| Calendar Time Zone | Necessary for Outlook Calendar but not included for Google Calendar. If you don't know your time zone string, you can add the action Convert To Time Zone to get it. | (UTC-08:00) Pacific Time (US & Canada) |
| Get past time - Begin Date | Set the date in the past to start getting shifts and creating events | 0 Months (now) |
| Get future time - End Date | Set the date in the future to start getting shifts and creating events | 3 Months |

**Limitations**
- [ ] Microsoft Teams actions are currently in preview action and don't support pagination; the maximum amount of shifts you can grab at a time are 100. If you have trouble getting all the shifts you want, you'll need to tweak the begin and end date to a shorter interval. This is especially true if you have a larger team since this flow must iterate through all team member's shifts.
- [ ] No current easy way via Power Automate to copy over the color of the shift to the calendar color. This isn't an option in create an event for Google Calendar or Outlook Calendar
- [ ] Possible timeouts may occur while iterating through the shifts though I haven't personally experienced them
- [ ] You must currently manually import the flow; I've submitted a request to put these flows in the Power Automate public gallery and hope they're approved so it's easier to setup!

Any issues and please open one up on this repository; I can't guarantee that I'll be able to fix your issue, but please open one up anyways!

<div style="text-align:center"><a href="https://www.buymeacoffee.com/vyKzl3x" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" style="height: 51px !important;width: 217px !important;" ></a></div>
