[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForUpdate.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForUpdate**

# TestWaitForUpdate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestWaitForUpdate(valueHandle * value, dword timeoutMs);
```

## Description

Waits for the next update of a **valueHandle**. This is equivalent to calling [TestWaitForUpdateCountGreater (value, value.GetUpdateCount(), timeoutMs)](CAPLfunctionTestWaitForUpdateCountGreater.md).

Note that only updates which occur while the function waits are considered. If you want to wait for updates which may occur earlier, or if you want to wait for several updates, use [TestWaitForUpdateFlag](CAPLfunctionTestWaitForUpdateFlag.md) or [TestWaitForUpdateCountGreater](CAPLfunctionTestWaitForUpdateCountGreater.md).

## Parameters

- **value**: Value handle of a communication object or distributed object.
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
ret = testWaitForUpdate(anEvent, 200);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [TestWaitForUpdateFlag](CAPLfunctionTestWaitForUpdateFlag.md) • [TestWaitForChange](CAPLfunctionTestWaitForChange.md) • [TestWaitForChangeCountGreater](CAPLfunctionTestWaitForChangeCountGreater.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)