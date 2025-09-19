[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitJ1939PGData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetWaitJ1939PGData

# TestGetWaitJ1939PGData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestGetWaitJ1939PGData (pg * aPG); // form 1`
- `long TestGetWaitJ1939PGData (dword index, pg * aPG); // form 2`

## Description

You can use this function to get the message content of J1939 Parameter Group that triggers a wait instruction.

Form 1 should be used if a wait operation for only one event is used (functions [TestWaitForJ1939PG](CAPLfunctionTestWaitForJ1939PG.md) or [TestWaitForJ1939DTC](CAPLfunctionTestWaitForJ1939DTC.md))

Form 2 can only be used for joined events. The number of the joined event (return value of [TestJoinJ1939PGEvent](CAPLfunctionTestJoinJ1939PGEvent.md) or [TestJoinJ1939DTCEvent](CAPLfunctionTestJoinJ1939DTCEvent.md)) is here being used as an index.

## Parameters

- **aPG**: J1939 parameter group variable that should be filled with this function.
- **index**: Number of the **joined event** corresponds with the return value of **testJoin...**.

## Return Values

- **0**: Data access successful.
- **-1**: Data access could not be executed, the last event was not a parameter group event.
- **-3**: The DLC is larger than the number of copied bytes in the parameter **aPG**. When initializing **aPG**, increase its DLC.

## Example

See examples of:

- [TestWaitForJ1939PG](CAPLfunctionTestWaitForJ1939PG.md)
- [TestWaitForJ1939DTC](CAPLfunctionTestWaitForJ1939DTC.md)
- [TestJoinJ1939PGEvent](CAPLfunctionTestJoinJ1939PGEvent.md)
- [TestJoinJ1939DTCEvent](CAPLfunctionTestJoinJ1939DTCEvent.md)

[TestWaitForJ1939PG](CAPLfunctionTestWaitForJ1939PG.md) • [TestJoinJ1939PGEvent](CAPLfunctionTestJoinJ1939PGEvent.md) • [TestWaitForJ1939DTC](CAPLfunctionTestWaitForJ1939DTC.md) • [TestJoinJ1939DTCEvent](CAPLfunctionTestJoinJ1939DTCEvent.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
