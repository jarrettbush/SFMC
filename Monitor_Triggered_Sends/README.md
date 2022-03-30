Monitor Triggered Sends
#######################

This process is responsible for ensuring triggered sends are in an active state. It is designed to highlight when a user, for example, republishes an email but forgets to start it running again.

This process will actively monitor:
* Manually created triggered send emails listed in the Triggered_Sends_Monitored_List data extension
* All emails in published journeys (where the journey name does not contain the word "test")

The process contains:
* An automation (Triggered Email Monitor) with a script activity (Triggered Email Monitor)
* A DE (Triggered_Sends_Monitored_List) for storing triggered sends you want to monitor (note journey monitoring is automatic)
* A DE (Triggered_Send_Error_Log) for logging triggered sends that aren't in an active state

Setup
-----
1. Use Package Manager to install the Monitor Triggered Sends process
2. Create a Server-to-Server Installed Package with, at a minimum:
  * Read access to Automations
  * Read access to Journeys
  * Read access to Lists and Subscribers
  * Read and Write access to Data Extensions
3. Add the triggered sends you'd like to monitor to the Triggered_Sends_Monitored_List data extension. You can toggle the Monitor field to true/false depending on if you want the script to check this triggered send
4. Update the MID and Installed Package info in the script activity
5. Set up appropriate email addresses in the Runtime Error or Skipped Run field on the automation so you are alerted when the automation picks up an email in a non-active state
