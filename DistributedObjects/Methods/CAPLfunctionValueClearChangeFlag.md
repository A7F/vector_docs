# valueHandle::ClearChangeFlag

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » valueHandle::ClearChangeFlag

## Method Syntax

[dword valueHandle::ClearChangeFlag()](../../../Shared/CAPL/General/ClassesAndObjects.md)

## Description

Clears the change flag of the value. It will be set again when the value changes the next time. You can wait for the flag to be set with [TestWaitForChangeFlag](../../Test/Functions/CAPLfunctionTestWaitForChangeFlag.md).

Using the change flag instead of waiting for a single change has the advantage that it doesn’t matter how many times the value is changed or in which order two values are changed.

## Parameters

—

## Return Values

—

## Example

```plaintext
long ret;
consumedEventRef * anEvent;
anEvent = lookupConsumedEvent(path);
anEvent.ClearChangeFlag();
// ...
ret = testWaitForChangeFlag(anEvent, 200);
```

## Related Links

- [Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
- [valueHandle::ClearUpdateFlag](CAPLfunctionValueClearUpdateFlag.md)
- [valueHandle::ResetValueState](CAPLfunctionValueResetValueState.md)
- [TestWaitForChangeFlag](../../Test/Functions/CAPLfunctionTestWaitForChangeFlag.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)