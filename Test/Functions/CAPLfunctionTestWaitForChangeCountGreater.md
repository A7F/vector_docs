[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForChangeCountGreater.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForChangeCountGreater

# TestWaitForChangeCountGreater

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestWaitForChangeCountGreater(valueHandle * value, qword count, dword timeoutMs);
```

## Description

Waits for the change counter of a **valueHandle** to reach a certain value. Each valueHandle contains a change counter which is reset to 0 at the start of measurement and with explicit calls to [valueHandle::ResetValueState](../../CommunicationObjects/Methods/CAPLfunctionValueResetValueState.md). You can read out the counter with [valueHandle::GetChangeCount](../../CommunicationObjects/Methods/CAPLfunctionValueGetChangeCount.md).

In case of a distributed object, this functionality is only available if the `[EnableChangeInfo]` attribute is enabled for the respective object.

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **count**: Change count to be reached.
- **timeoutMS**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred (value has changed)

## Example

```plaintext
long ret;
consumedEventRef * anEvent;
anEvent = lookupConsumedEvent(path);
// ...
ret = testWaitForChangeCountGreater(anEvent, anEvent.GetChangeCount() + 3, 200);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [TestWaitForChangeFlag](CAPLfunctionTestWaitForChangeFlag.md) • [TestWaitForChange](CAPLfunctionTestWaitForChange.md) • [TestWaitForUpdateCountGreater](CAPLfunctionTestWaitForUpdateCountGreater.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)