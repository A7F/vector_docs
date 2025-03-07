[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinFrSymbolEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinFrSymbolEvent

# TestJoinFrSymbolEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinFrSymbol ()`
- `long TestJoinFrSymbol (dword aSymbolType, dword aChannelMask)`

## Description

Completes the current set of "joined events" with the FlexRay symbol event. This function does not wait.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aSymbolType**: Identifies the type of symbol the function will wait for.
  - `0`: unknown
  - `1`: CAS
  - `2`: MTS
  - `3`: Wakeup

- **aChannelMask**: Identifies the FlexRay channel of the communication controller. A value of 1 will wait for the symbol on channel A, 2 will wait for it on channel B and 3 on any channel (A/B).

## Return Values

- `-3`: Join error
- `-1`: General error, for example, functionality is not available
- `> 0`: Number of the joined event

## Example

For an example see function [TestWaitForFrSymbol](CAPLfunctionTestWaitForFrSymbol.md).

[TestWaitForFrSymbol](CAPLfunctionTestWaitForFrSymbol.md) • [TestGetWaitFrSymbolData](CAPLfunctionTestGetWaitFrSymbolData.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)