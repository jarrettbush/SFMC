Workspace for SFMC code that I don't want to lose. Requirements for any given code sample will reside here.

Enterperise Automations
#######################
A Cloud Page designed to sit in the Parent Business Unit that shows all the automations across the Enterprise, their status, the last time they were run and the next scheduled time for them to run.

Data needs to be updated in one location:
Line 25 - External Key of Enterprise_Automations data extension

Requirements:
Runs off a data extension called Enterprise_Automations.

Field            Type          PK          Nullable
CustomerKey      Text(255)     Y           N
MID              Text(10)                  Y
AutoName         Text(255)                 Y
AutoStatusNum    Number                    Y
AutoStatus       Text(50)                  Y
LastRunTime      Date                      Y
ScheduledTime    Date                      Y
IsActive         Boolean                   Y
BU_Name          Text(255)                 Y
AutoStatusClass  Text(100)                 Y
