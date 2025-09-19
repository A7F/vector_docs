[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForUpdateFlag.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForUpdateFlag

# TestWaitForUpdateFlag

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestWaitForUpdateFlag(valueHandle * value, dword timeoutMs);
```

## Description

Waits for the update flag of a **valueHandle** to be set. Each valueHandle has an update flag which is set when the value is updated and reset through an explicit call to [valueHandle::ClearUpdateFlag](../../CommunicationObjects/Methods/CAPLfunctionValueClearUpdateFlag.md) or [valueHandle::ResetValueState](../../CommunicationObjects/Methods/CAPLfunctionValueResetValueState.md).

Use this function instead of [TestWaitForUpdate](CAPLfunctionTestWaitForUpdate.md) if an undetermined number of updates may occur between a point where you reset the flag and a point where at least one update must have occurred.

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **timeoutMS**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred (update flag was set)

## Example

```c
long ret;
consumedEventRef * anEvent;
anEvent = lookupConsumedEvent(path);
anEvent.ClearUpdateFlag();
// ...
ret = testWaitForUpdateFlag(anEvent, 200);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [TestWaitForUpdate](CAPLfunctionTestWaitForUpdate.md) • [TestWaitForChange](CAPLfunctionTestWaitForChange.md) • [TestWaitForChangeFlag](CAPLfunctionTestWaitForChangeFlag.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
