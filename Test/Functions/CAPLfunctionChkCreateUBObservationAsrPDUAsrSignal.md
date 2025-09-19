[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateUBObservationAsrPDUAsrSignal.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_UBObservationAsrPDU, ChkStart_UBObservationAsrPDU, ChkCreate_UBObservationAsrSignal, ChkStart_UBObservationAsrSignal

# ChkCreate_UBObservationAsrPDU, ChkStart_UBObservationAsrPDU, ChkCreate_UBObservationAsrSignal, ChkStart_UBObservationAsrSignal

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_UBObservationAsrPDU(PDU aPDU, dword maxNoOfConsUnchangedDataWithSetUB);`
- `dword ChkStart_UBObservationAsrPDU(PDU aPDU, dword maxNoOfConsUnchangedDataWithSetUB);`
- `dword ChkCreate_UBObservationAsrPDU(PDU aPDU, char [] signalGroup, dword maxNoOfConsUnchangedDataWithSetUB);`
- `dword ChkStart_UBObservationAsrPDU(PDU aPDU, char [] signalGroup, dword maxNoOfConsUnchangedDataWithSetUB);`
- `dword ChkCreate_UBObservationAsrPDU(long aHeaderId, dword maxNoOfConsUnchangedDataWithSetUB);`
- `dword ChkStart_UBObservationAsrPDU(long aHeaderId, dword maxNoOfConsUnchangedDataWithSetUB);`
- `dword ChkCreate_UBObservationAsrPDU(long aHeaderId, char [] signalGroup, dword maxNoOfConsUnchangedDataWithSetUB);`
- `dword ChkStart_UBObservationAsrPDU(long aHeaderId, char [] signalGroup, dword maxNoOfConsUnchangedDataWithSetUB);`
- `dword ChkCreate_UBObservationAsrSignal(long aHeaderId, char [] signalName, dword maxNoOfConsUnchangedDataWithSetUB);`
- `dword ChkStart_UBObservationAsrSignal(long aHeaderId, char [] signalName, dword maxNoOfConsUnchangedDataWithSetUB);`
- `dword ChkCreate_UBObservationAsrSignal(PDU aPDU, char [] signalName, dword maxNoOfConsUnchangedDataWithSetUB);`
- `dword ChkStart_UBObservationAsrSignal(PDU aPDU, char [] signalName, dword maxNoOfConsUnchangedDataWithSetUB);`

## Constructor

- `TestCheck::CreateUBObservationAsrPDU(PDU aPDU, dword maxNoOfConsUnchangedDataWithSetUB);`
- `TestCheck::StartUBObservationAsrPDU(PDU aPDU, dword maxNoOfConsUnchangedDataWithSetUB);`
- `TestCheck::CreateUBObservationAsrPDU(PDU aPDU, char [] signalGroup, dword maxNoOfConsUnchangedDataWithSetUB);`
- `TestCheck::StartUBObservationAsrPDU(PDU aPDU, char [] signalGroup, dword maxNoOfConsUnchangedDataWithSetUB);`
- `TestCheck::CreateUBObservationAsrPDU(long aHeaderId, dword maxNoOfConsUnchangedDataWithSetUB);`
- `TestCheck::StartUBObservationAsrPDU(long aHeaderId, dword maxNoOfConsUnchangedDataWithSetUB);`
- `TestCheck::CreateUBObservationAsrPDU(long aHeaderId, char [] signalGroup, dword maxNoOfConsUnchangedDataWithSetUB);`
- `TestCheck::StartUBObservationAsrPDU(long aHeaderId, char [] signalGroup, dword maxNoOfConsUnchangedDataWithSetUB);`
- `TestCheck::StartUBObservationAsrSignal(long aHeaderId, char [] signalName, dword maxNoOfConsUnchangedDataWithSetUB);`
- `TestCheck::StartUBObservationAsrSignal(long aHeaderId, char [] signalName, dword maxNoOfConsUnchangedDataWithSetUB);`
- `TestCheck::CreateUBObservationAsrSignal(PDU aPDU, char [] signalName, dword maxNoOfConsUnchangedDataWithSetUB);`
- `TestCheck::StartUBObservationAsrSignal(PDU aPDU, char [] signalName, dword maxNoOfConsUnchangedDataWithSetUB);`

## Check Name

[AUTOSAR UB Observation](../../../TestCommands/CheckDescriptions/CDAUTOSARUBObservation.md)

## Description

Monitors the UB of a PDU, a single signal group of a PDU or a single signal of a PDU. The check condition is violated if the UB of a signal is set and the matching signal is not changed in the PDU or signal group. The check can be set up for a single PDU, a single signal group within a PDU or a single signal with a PDU.

The functions/constructors without the parameter **signalGroup** monitor all specified UB's within the given PDU.

The numeric functions/constructors with the parameter **aHeaderId** cannot be used for FlexRay.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aPDU**: Must exist in DB
- **aHeaderId**: PDU header ID to be observed. The corresponding PDU shall be defined in the database.
- **signalGroup**: Signal group with SQC to be observed.
- **signalName**: Signal with UB to be observed.
- **maxNoOfConsUnchangedDataWithSetUB**:
  - `> 0`: Maximal number of constant unchanged data with set UB
  - `= 0`: Unchanged data with set UB not allowed
  - `-1`: Unchanged data with set UB allowed infinite

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- Specified PDU object does not exist in the database.
- Given PDU or signal group does not contain a SQC signal.

## Example

```cpp
// checks the payload gaps of the message
checkId = ChkStart_UBObservationAsrPDU (PDUToObserve, "signalGroup1");
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
