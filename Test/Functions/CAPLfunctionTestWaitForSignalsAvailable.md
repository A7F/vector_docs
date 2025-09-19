[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForSignalsAvailable.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForSignalsAvailable

# TestWaitForSignalsAvailable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function replaces `TestWaitForSignals`.

## Function Syntax

```
long TestWaitForSignalsAvailable (dbNode aNode, dword aTimeout);
```

## Description

Tests the availability of all the send signals of a node and waits if necessary until all the send signals of the node are available. Signals that are received at least once from the bus after the measurement starts are classified as "available".

This function is useful when you want to assure that all signals are available before starting a signal-based test, i.e. to synchronize the tester with the bus.

## Parameters

- **aNode**  
  Node whose send signals should all be available. For CAN and FlexRay all signals are considered! In contrast to the corresponding XML pattern `<awaitsignalsavailable>` this function considers FlexRay signals from all frames and PDUs; not only FlexRay signals from frames and PDUs of service type 'Application'. For LIN nodes only signals from unconditional and event-triggered frames of all schedule tables are considered. Also the signals of diagnostic frames are ignored.

- **aTimeout**  
  Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-2**  
  Wait state is exited due to a constraint/condition violation

- **-1**  
  General error, e.g. functionality is unavailable

- **0**  
  Wait state is exited due to a timeout; not all signals are available

- **1**  
  The wait state is exited; all of the node’s send signals are available for further tests

## Example

```c
// waits for the availability of all tx signals of node ‘SUT’
long result;
result = TestWaitForSignalsAvailable(SUT, 2000);
```

[TestWaitForSignalAvailable](CAPLfunctionTestWaitForSignalAvailable.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
