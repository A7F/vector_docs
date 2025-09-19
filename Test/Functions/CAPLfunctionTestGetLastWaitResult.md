[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetLastWaitResult.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetLastWaitResult

# TestGetLastWaitResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestGetLastWaitResult();
```

## Description

Makes available the last occurred return value of a TestWait instruction once again.

## Parameters

—

## Return Values

See TestWait instructions

## Example

```plaintext
TestWaitForTimeout(100);
Write("Waiting Result = %d", TestGetLastWaitResult());
```

[TestWaitForMessage](CAPLfunctionTestWaitForMessage.md) • [TestWaitForAuxEvent](CAPLfunctionTestWaitForAuxEvent.md) • [TestWaitForTextEvent](CAPLfunctionTestWaitForTextEvent.md) • [TestWaitForTimeout](CAPLfunctionTestWaitForTimeout.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
