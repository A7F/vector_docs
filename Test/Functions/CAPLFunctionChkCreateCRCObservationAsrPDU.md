[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLFunctionChkCreateCRCObservationAsrPDU.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_CRCObservationAsrPDU, ChkStart_CRCObservationAsrPDU

# ChkCreate_CRCObservationAsrPDU, ChkStart_CRCObservationAsrPDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_CRCObservationAsrPDU(PDU aPDU);`
- `dword ChkStart_CRCObservationAsrPDU(PDU aPDU);`
- `dword ChkCreate_CRCObservationAsrPDU(PDU aPDU, char [] signalGroup);`
- `dword ChkStart_CRCObservationAsrPDU(PDU aPDU, char [] signalGroup);`
- `dword ChkCreate_CRCObservationAsrPDU(long aHeaderId);`
- `dword ChkStart_CRCObservationAsrPDU(long aHeaderId);`
- `dword ChkCreate_CRCObservationAsrPDU(long aHeaderId, char [] signalGroup);`
- `dword ChkStart_CRCObservationAsrPDU(long aHeaderId, char [] signalGroup);`

## [Constructor](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::CreateCRCObservationAsrPDU(PDU aPDU);`
- `TestCheck::StartCRCObservationAsrPDU(PDU aPDU);`
- `TestCheck::CreateCRCObservationAsrPDU(PDU aPDU, char [] signalGroup);`
- `TestCheck::StartCRCObservationAsrPDU(PDU aPDU, char [] signalGroup);`
- `TestCheck::CreateCRCObservationAsrPDU(long aHeaderId);`
- `TestCheck::StartCRCObservationAsrPDU(long aHeaderId);`
- `TestCheck::CreateCRCObservationAsrPDU(long aHeaderId, char [] signalGroup);`
- `TestCheck::StartCRCObservationAsrPDU(long aHeaderId, char [] signalGroup);`

## Check Name

[AUTOSAR CRC Observation](../../../TestCommands/CheckDescriptions/CDAUTOSARCRCObservation.md) check

## Description

This check monitors the CRC of a PDU or a single signal group of a PDU. The check condition is violated if the calculated CRC does not match the value of the CRC signal contained in the PDU or signal group. The check can be set up for a single PDU or a single signal group within a PDU.

The functions/constructors without the parameter **signalGroup** monitor all specified CRCs within the given PDU.

The numeric functions/constructors with the parameter **aHeaderId** cannot be used for FlexRay.

**Note**: Dependent on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aPDU**: Must exist in the database.
- **aHeaderId**: PDU header ID to be observed. The corresponding PDU shall be defined in the database.
- **signalGroup**: CRC of signal group to be observed.

## Return Values

- **0**: Check could not be created and must not be referenced.
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Specified PDU object does not exist in the database.
- Given PDU or signal group does not contain a CRC signal.

## Example

```cpp
// checks the payload gaps of the message
checkId = ChkStart_CRCObservationAsrPDU (PDUToObserve, "signalGroup1");
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
