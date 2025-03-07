[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/EventProcedures/CAPLfunctionOnFRPocState.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » on frPOCState

# on frPOCState

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

`on frPOCState;`

## Description

The event procedure is called whenever there is a change of state on the FlexRay Communication Controller's protocol operation state machine.

## Parameters

—

## Selectors

- **Time (data type dword) / Time_ns (data type int64)**
  - The transition time stamp that has been synchronized with the global time base in the computer (CAN hardware or computer system clock).
  - The time stamp must be used if time relations should be regarded with events from other sources. This time stamp is also output in the Trace Window when receiving a symbol.
  - Timer unit: 10 microseconds.
  - NS timer unit: nanoseconds.
  - **Write-protected!**

- **MsgChannel**
  - Channel in the tool that the FlexRay CC determines.
  - **Write-protected!**

- **FR_POCState**
  - The POC state of the E-Ray and the cold-start helper CC can be changed with the function [FrSetPocState](../Functions/CAPLfunctionFRSetPocState.md). If the desired POC-state is reached, then this event is generated.
  - Identifies the new state of the POC state machine (data type LONG):
    - **E-Ray**: -2, **Coldstart Helper**: 254, **POC State**: SYNC LOST
    - **E-Ray**: -1, **Coldstart Helper**: 255, **POC State**: UNKNOWN
    - **E-Ray**: 0, **Coldstart Helper**: 256, **POC State**: DEFAULT CONFIG
    - **E-Ray**: 1, **Coldstart Helper**: 257, **POC State**: READY
    - **E-Ray**: 2, **Coldstart Helper**: 258, **POC State**: NORMAL ACTIVE
    - **E-Ray**: 3, **Coldstart Helper**: 259, **POC State**: NORMAL PASSIVE
    - **E-Ray**: 4, **Coldstart Helper**: 260, **POC State**: HALT
    - **E-Ray**: 5, **Coldstart Helper**: 261, **POC State**: MONITOR MODE
    - **E-Ray**: 15, **Coldstart Helper**: 262, **POC State**: CONFIG
    - **E-Ray**: 16, **Coldstart Helper**: 263, **POC State**: WAKEUP STANDBY
    - **E-Ray**: 17, **Coldstart Helper**: 264, **POC State**: WAKEUP LISTEN
    - **E-Ray**: 18, **Coldstart Helper**: 265, **POC State**: WAKEUP SEND
    - **E-Ray**: 19, **Coldstart Helper**: 266, **POC State**: WAKEUP DETECT
    - **E-Ray**: 32, **Coldstart Helper**: 267, **POC State**: STARTUP PREPARE
    - **E-Ray**: 33, **Coldstart Helper**: 268, **POC State**: COLDSTART LISTEN
    - **E-Ray**: 34, **Coldstart Helper**: 269, **POC State**: COLDSTART COLLISION RESOLUTION
    - **E-Ray**: 35, **Coldstart Helper**: 270, **POC State**: COLDSTART CONSISTENCY CHECK
    - **E-Ray**: 36, **Coldstart Helper**: 271, **POC State**: COLDSTART GAP
    - **E-Ray**: 37, **Coldstart Helper**: 272, **POC State**: COLDSTART JOIN
    - **E-Ray**: 38, **Coldstart Helper**: 273, **POC State**: INTEGRATION COLDSTART CHECK
    - **E-Ray**: 39, **Coldstart Helper**: 274, **POC State**: INTEGRATION LISTEN
    - **E-Ray**: 40, **Coldstart Helper**: 275, **POC State**: INTEGRATION CONSISTENCY CHECK
    - **E-Ray**: 41, **Coldstart Helper**: 276, **POC State**: INITIALIZE SCHEDULE
    - **E-Ray**: 42, **Coldstart Helper**: 277, **POC State**: ABORT STARTUP
    - **E-Ray**: 43, **Coldstart Helper**: 278, **POC State**: STARTUP SUCCESS
    - **E-Ray**: 100, **Coldstart Helper**: —, **POC State**: RESERVED FOR INTERNAL USE
  - **Write-protected!**

- **Type**
  - Identifies the FlexRay hardware type (data type: dword)
    - 0: HW Independent
    - 1: Invalid
    - 2: Not used
    - 3: Not used
    - 4: FlexCard Cyclone II
    - 5: VN
    - 6: Reserved for internal use
  - **Write-protected!**

- **FR_Info1**
  - Contains extended information (data type: dword):
  - If Type == 1:
    - 0: Interface is synchronized, but passive
    - 1: Interface is synchronized and active
    - 2: Interface is not synchronized
    - 3: Unknown
  - **Write-protected!**

- **FR_Info2**
  - Contains extended information (data type: dword):
    - 0: WAKEUP UNDEFINED
    - 1: WAKEUP RECEIVED HEADER
    - 2: WAKEUP RECEIVED WUP
    - 3: WAKEUP COLLISION HEADER
    - 4: WAKEUP COLLISION WUP
    - 5: WAKEUP COLLISION UNKNOWN
    - 6: WAKEUP TRANSMITTED
    - 7: WAKEUP RECEIVED (Only with VN interfaces)
    - 16: WUP DETECTED (Only with VN interfaces)
  - **Write-protected!**

- **FR_Info3**
  - Contains extended information (data type: dword): Not used as yet.
  - **Write-protected!**

- **FR_Info4**
  - Contains extended information (data type: dword).
  - **FR_POCState** is set to -1 and **FR_Info4** is set to 1, when the trigger input of the VN interface has recognized an appropriate edge.
  - **Write-protected!**

- **FR_Cycle**
  - Current FlexRay cycle number.
  - **Write-protected!**

## Example

The following program reacts on Protocol Operation Control state changes in the FlexRay interface and prints them in the Write Window, Trace Window, and logging.

```plaintext
variables
{
   const int cWriteTextSize = 512;
   char writeTxt[cWriteTextSize];
   const int cWriteTextSize2 = 40;
   char writeTxt2[cWriteTextSize2];
   const int writeSink_Trace          = -3;
   const int writeSink_Logging        = -2;
   const int writeSeverity_Information = 1;
   int gClusterIsAsync = -1;
}

on frPocState
{
   getPOCStateName(this.FR_POCState, cWriteTextSize2, writeTxt2);
   snprintf(writeTxt, cWriteTextSize, "%10.6f: on FRPOCState %2d (%-32s) in cycle %3d on channel %2d with HW Type %2d, Info1 0x%02x, Info2 0x%02x, Info3 0x%02x, Info4 0x%02x.", getTime(0), this.FR_POCState, writeTxt2, this.FR_Cycle, (int)this.MsgChannel, this.Type, this.FR_Info1, this.FR_Info2, this.FR_Info3, this.FR_Info4);
   myprint(writeTxt);
   output(this); // only required in Measurement Setup
   if ((this.FR_POCState != -1) && (this.FR_POCState < 100)) {
      if (((gClusterIsAsync == -1) || (gClusterIsAsync == 0)) && ((this.FR_POCState == 4) || (this.FR_POCState == -2))) {
         gClusterIsAsync = 1;
         write("gClusterIsAsync = 1");
      }
      if (((gClusterIsAsync == -1) || (gClusterIsAsync == 1)) && (this.FR_POCState == 2)) {
         gClusterIsAsync = 0;
         write("gClusterIsAsync = 0");
      }
   }
}

float getTime (float time)
{
   return TimeNowNS() / 1000000000.0;
}

void myprint(char text[])
{
   write("%s", text);
   writeLineEx(writeSink_Trace,   writeSeverity_Information, "%s", text);
   writeLineEx(writeSink_Logging, writeSeverity_Information, "%s", text);
}

int getPOCStateName (int state, word nameSize, char name[])
{
   int r = -1;
   if (state == -2) {
      snprintf(name, nameSize, "Synchronization Lost");
      r = state;
   } else if (state == 0x00) {
      snprintf(name, nameSize, "Default Config");
      r = state;
   } else if (state == 0x01) { 
      snprintf(name, nameSize, "Ready");
      r = state;
   } else if (state == 0x02) { 
      snprintf(name, nameSize, "Normal Active");
      r = state;
   } else if (state == 0x03) { 
      snprintf(name, nameSize, "Normal Passive");
      r = state;
   } else if (state == 0x04) { 
      snprintf(name, nameSize, "Halt");
      r = state;
   } else if (state == 0x05) { 
      snprintf(name, nameSize, "Monitor Mode");
      r = state;
   } else if (state == 0x0f) { 
      snprintf(name, nameSize, "Config");
      r = state;
   } else if (state == 0x10) { 
      snprintf(name, nameSize, "Wakeup Standby");
      r = state;
   } else if (state == 0x11) { 
      snprintf(name, nameSize, "Wakeup Listen");
      r = state;
   } else if (state == 0x12) { 
      snprintf(name, nameSize, "Wakeup Send");
      r = state;
   } else if (state == 0x13) { 
      snprintf(name, nameSize, "Wakeup Detect");
      r = state;
   } else if (state == 0x20) { 
      snprintf(name, nameSize, "Startup Prepare");
      r = state;
   } else if (state == 0x21) { 
      snprintf(name, nameSize, "Coldstart Listen");
      r = state;
   } else if (state == 0x22) { 
      snprintf(name, nameSize, "Coldstart Collision Resolution");
      r = state;
   } else if (state == 0x23) { 
      snprintf(name, nameSize, "Coldstart Consistency Check");
      r = state;
   } else if (state == 0x24) { 
      snprintf(name, nameSize, "Coldstart Gap");
      r = state;
   } else if (state == 0x25) { 
      snprintf(name, nameSize, "Coldstart Join");
      r = state;
   } else if (state == 0x26) { 
      snprintf(name, nameSize, "Integration Coldstart Check");
      r = state;
   } else if (state == 0x27) { 
      snprintf(name, nameSize, "Integration Listen");
      r = state;
   } else if (state == 0x28) { 
      snprintf(name, nameSize, "Integration Consistency Check");
      r = state;
   } else if (state == 0x29) { 
      snprintf(name, nameSize, "Initialize Schedule");
      r = state;
   } else if (state == 0x2a) { 
      snprintf(name, nameSize, "Abort Startup");
      r = state;
   } else if (state == 0x2b) { 
      snprintf(name, nameSize, "Startup Success");
      r = state;
   } else { 
      snprintf(name, nameSize, "Unknown");
      r = -1;
   }
   return r;
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)