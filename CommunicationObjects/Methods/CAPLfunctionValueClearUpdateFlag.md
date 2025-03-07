# valueHandle::ClearUpdateFlag (obsolete)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » valueHandle::ClearUpdateFlag

**Valid for:** CANoe DE

## Method Syntax

`dword valueHandle::ClearUpdateFlag()`

## Description

Clears the update flag of the value. It will be set again when the value is updated the next time. You can wait for the flag to be set with [TestWaitForUpdateFlag](../../Test/Functions/CAPLfunctionTestWaitForUpdateFlag.md).

Using the update flag instead of waiting for a single update has the advantage that it doesn’t matter how many times the value is updated or in which order two values are updated.

## Parameters

—

## Return Values

—

## Example

```plaintext
long ret;
consumedEventRef * anEvent;
anEvent = lookupConsumedEvent(path);
anEvent.ClearUpdateFlag();
// ...
ret = testWaitForUpdateFlag(anEvent, 200);
```

## Related Links

- [Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
- [valueHandle::ClearChangeFlag](CAPLfunctionValueClearChangeFlag.md)
- [valueHandle::ResetValueState](CAPLfunctionValueResetValueState.md)
- [TestWaitForChangeFlag](../../Test/Functions/CAPLfunctionTestWaitForChangeFlag.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)