[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForReplay.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForReplay**

# TestWaitForReplay

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
long TestWaitForReplay(char file[]);
```

## Description

Starts playing the replay file with the name **file** and waits until the execution has been finished.

This function replays events of the following types:

- CAN messages
- CAN Error Frames
- CAN overload frames (not sent, only visible in Measurement Setup)
- J1708 messages
- Ethernet packets
- WLAN packets
- AFDX packets
- Diagnostic requests
- GPS events
- Signal values
- System variable updates
- Environment variable updates

In particular, replay of LIN, FlexRay, and MOST events using this function is not possible.

All events are replayed on the same channel as they are recorded in the replay file. Events targeted to non-configured channels are discarded.

The first event in the replay file is replayed immediately, disregarding its time stamp.

The start of replay is timely decoupled from calling this function, so replay will actually start a short but indeterminate time span after this function returns.

The function is not allowed in [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md). Errors are reported as **error in test system** or **fail** in case of 2-valued verdict concept.

## Parameters

- **file**: Replay file.

## Return Values

- **-1**: Invalid path or unable to load replay file.
- **-999**: Aborted by end of measurement.
- **1**: Replay executed successfully.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
