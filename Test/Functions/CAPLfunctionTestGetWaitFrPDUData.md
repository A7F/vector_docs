[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitFrPDUData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetWaitFrPDUData

# TestGetWaitFrPDUData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestGetWaitFrPDUData (frPDU aPDU);
long TestGetWaitFrPDUData (dword index, frPDU aPDU);
```

## Description

If a valid FlexRay PDU is the last event that triggers a wait instruction, the PDU’s content can be called up with the first function.

The second function can only be used for "joined events". The number of the "joined event" (return value of "testJoin...") is here being used as an index.

## Parameters

- **aPDU**: PDU variable of type [FrPDU](../../FlexRay/Objects/CAPLfunctionFrPDU.md) that should be filled in with this function.
- **Index**: Number of the "joined event" corresponds with the return value of "testJoin...".

## Return Values

- **0**: Data access successful
- **-1**: Data access could not be executed, the last event was not a FlexRay PDU event

## Example

For an example see function [TestWaitForFrPDU](CAPLfunctionTestWaitForFrPDU.md).

[TestWaitForFrPDU](CAPLfunctionTestWaitForFrPDU.md) • [TestJoinFrPDUEvent](CAPLfunctionTestJoinFrPDUEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
