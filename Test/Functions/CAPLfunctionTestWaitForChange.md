[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForChange.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForChange

# TestWaitForChange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestWaitForChange(valueHandle * value, dword timeoutMs);
```

## Description

Waits for the next change of a **valueHandle**. This is equivalent to calling [TestWaitForChangeCountGreater (value, value.GetChangeCount(), timeoutMs)](CAPLfunctionTestWaitForChangeCountGreater.md).

Note that only changes which occur while the function waits are considered. If you want to wait for changes which may occur earlier, or if you want to wait for several changes, use [TestWaitForChangeFlag](CAPLfunctionTestWaitForChangeFlag.md) or [TestWaitForChangeCountGreater](CAPLfunctionTestWaitForChangeCountGreater.md).

In case of a distributed object, this functionality is only available if the `[EnableChangeInfo]` attribute is enabled for the respective object.

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **timeoutMS**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred (method was called)

## Example

```plaintext
long ret;
consumedEventRef * anEvent;
anEvent = lookupConsumedEvent(path);
// ...
ret = testWaitForChange(anEvent, 200);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [TestWaitForChangeFlag](CAPLfunctionTestWaitForChangeFlag.md) • [TestWaitForUpdate](CAPLfunctionTestWaitForUpdate.md) • [TestWaitForUpdateCountGreater](CAPLfunctionTestWaitForUpdateCountGreater.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
