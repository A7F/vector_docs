[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitPDUData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetWaitPDUData

# TestGetWaitPDUData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestGetWaitPDUData (PDU * aPDU); // form 1`
- `long TestGetWaitPDUData (dword explicitJoinIndex, PDU * aPDU); // form 2`

## Description

If a valid PDU is the last event that triggers a wait instruction, the PDU’s content can be called up with form 1.

Form 2 can only be used for **joined events**. The number of the **joined event** (return value of `TestJoin...`) is here being used as an index.

## Parameters

- **aPDU**: PDU variable of type PDU that should be filled in with this function. It has to be either a type free PDU variable, or a PDU variable that was created for the PDU type that triggered the wait instruction.
- **explicitJoinIndex**: Number of the **joined event** corresponds with the return value of `TestJoin...`.

## Return Values

- **0**: Data access successful.
- **-1**: Data access could not be executed, the last event was not a PDU event.
- **-2**: Data access could not be executed; the **explicitJoinIndex** is out-of-range.
- **-7**: Parameter **aPDU** is a typed PDU variable, but the returned PDU has a different type.

## Example

—

[TestJoinPDUEvent](CAPLfunctionTestJoinPDUEvent.md) • [TestWaitForPDU](CAPLfunctionTestWaitForPDU.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)