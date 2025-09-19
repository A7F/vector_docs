[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForUpdateCountGreater.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForUpdateCountGreater

# TestWaitForUpdateCountGreater

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestWaitForUpdateCountGreater(valueHandle * value, qword count, dword timeoutMs);
```

## Description

Waits for the update counter of a **valueHandle** to reach a certain value. Each valueHandle contains an update counter which is reset to 0 at the start of measurement and with explicit calls to [valueHandle::ResetValueState](../../CommunicationObjects/Methods/CAPLfunctionValueResetValueState.md). You can read out the counter with [valueHandle::GetUpdateCount](../../CommunicationObjects/Methods/CAPLfunctionValueGetUpdateCount.md).

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **count**: Update count to be reached.
- **timeoutMS**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred (value was updated)

## Example

```plaintext
long ret;
consumedEventRef * anEvent;
anEvent = lookupConsumedEvent(path);
// ...
ret = testWaitForUpdateCountGreater(anEvent, anEvent.GetUpdateCount() + 3, 200);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [TestWaitForUpdateFlag](CAPLfunctionTestWaitForUpdateFlag.md) • [TestWaitForUpdate](CAPLfunctionTestWaitForUpdate.md) • [TestWaitForChange](CAPLfunctionTestWaitForChange.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
