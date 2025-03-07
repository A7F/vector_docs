[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinUpdateCountGreater.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinUpdateCountGreater

# TestJoinUpdateCountGreater

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestJoinUpdateCountGreater(valueHandle * value);
```

## Description

Completes the current set of **joined events** with the transmitted event. This function does not wait.

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **count**: Change count to be reached.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```c
long ret;
consumedEventRef * anEvent;
anEvent = lookupConsumedEvent(path);
// ...
ret = testJoinUpdateCountGreater(anEvent, anEvent.GetChangeCount() + 3);
index = TestWaitForAllJoinedEvents(2000);
```

[TestJoinUpdate](CAPLfunctionTestJoinUpdate.md) • [TestJoinUpdateFlag](CAPLfunctionTestJoinUpdateFlag.md) • [TestJoinChangeCountGreater](CAPLfunctionTestJoinChangeCountGreater.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)