[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitFrSymbolData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetWaitFrSymbolData

# TestGetWaitFrSymbolData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestGetWaitFrSymbolData (FrSymbol aSymbol);
long TestGetWaitFrSymbolData (dword index, FrSymbol aSymbol);
```

## Description

If a FlexRay symbol event is the last event that triggers a wait instruction, the event’s content can be called up with the first function.

The second function can only be used for "joined events". The number of the "joined event" (return value of "testJoin...") is here being used as an index.

## Parameters

- **aSymbol**: Event structure that should be filled in with this function (for selectors see event procedure [on FRSymbol](../../FlexRay/EventProcedures/CAPLfunctionOnFRSymbol.md)).
- **Index**: Number of the "joined event" corresponds with the return value of "testJoin...".

## Return Values

- **0**: Data access successful
- **-1**: Data access could not be executed, the last event was not a FlexRay POC event

## Example

For an example see function [TestWaitForFrSymbol](CAPLfunctionTestWaitForFrSymbol.md).

[TestWaitForFrPOCState](CAPLfunctionTestWaitForFrSymbol.md) • [TestJoinFrSymbolEvent](CAPLfunctionTestJoinFrSymbolEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)