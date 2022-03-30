Required Automation Tracker
---------------------------

This process is responsible for tracking if business-critical automations are running according to their defined schedule. It is designed to highlight when a user, for example, pauses an automation and forgets to make it active again.

This process is designed to run on a daily basis and allows you to set a minimum run-time (based in days) for any automation.

The Required_Automation_Register data extension contains 3 fields:
1. AutomationName - The exact name of the automation you want to track
2. MinDaysBetweenRuns - The expected gap in days between run times of your automation eg a daily automation would be 1, weekly would be 7
3. InProduction - Toggle this field if you need to stop an automation from being monitored. True means the automation is monitored, false means it will be skipped

The process contains:
* An automation (Required Automation Checker) with a script activity (Required Automation Checker) and a verification step
* A DE (Required_Automation_Register) for storing automations you want to monitor
* A DE (Required_Automation_Error_List) for logging automations that have not run in their expected time

Setup
-----
1. Use Package Manager to install the Required Automation Checker process
2. Add the automations you'd like to monitor to the Required_Automation_Register data extension
3. Set up appropriate email addresses in the Runtime Error or Skipped Run field on the automation so you are alerted when the automation picks up an automation that hasn't run according to its schedule
