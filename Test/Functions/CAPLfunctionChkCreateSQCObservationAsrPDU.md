[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateSQCObservationAsrPDU.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_SQCObservationAsrPDU, ChkStart_SQCObservationAsrPDU

# ChkCreate_SQCObservationAsrPDU, ChkStart_SQCObservationAsrPDU

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_SQCObservationAsrPDU(PDU aPDU);`
- `dword ChkStart_SQCObservationAsrPDU(PDU aPDU);`
- `dword ChkCreate_SQCObservationAsrPDU(PDU aPDU, char [] signalGroup);`
- `dword ChkStart_SQCObservationAsrPDU(PDU aPDU, char [] signalGroup);`
- `dword ChkCreate_SQCObservationAsrPDU(long aHeaderId);`
- `dword ChkStart_SQCObservationAsrPDU(long aHeaderId);`
- `dword ChkCreate_SQCObservationAsrPDU(long aHeaderId, char [] signalGroup);`
- `dword ChkStart_SQCObservationAsrPDU(long aHeaderId, char [] signalGroup);`

## Constructor

- `TestCheck::CreateSQCObservationAsrPDU(PDU aPDU);`
- `TestCheck::StartSQCObservationAsrPDU(PDU aPDU);`
- `TestCheck::CreateSQCObservationAsrPDU(PDU aPDU, char [] signalGroup);`
- `TestCheck::StartSQCObservationAsrPDU(PDU aPDU, char [] signalGroup);`
- `TestCheck::CreateSQCObservationAsrPDU(long aHeaderId);`
- `TestCheck::StartSQCObservationAsrPDU(long aHeaderId);`
- `TestCheck::CreateSQCObservationAsrPDU(long aHeaderId, char [] signalGroup);`
- `TestCheck::StartSQCObservationAsrPDU(long aHeaderId, char [] signalGroup);`

## Check Name

[AUTOSAR SQC Observation](../../../TestCommands/CheckDescriptions/CDAUTOSARSQCObservation.md)

## Description

Monitors the SQC of a PDU or a single signal group of a PDU. The check condition is violated if the last SQC does not match to the current contained in the PDU or signal group. The check can be set up for a single PDU or a single signal group within a PDU.

The functions/constructors without the parameter **signalGroup** monitors all specified SQC's within the given PDU.

The numeric functions/constructors with the parameter **aHeaderId** cannot be used for FlexRay.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aPDU**: Must exist in DB
- **aHeaderId**: PDU header ID to be observed. The corresponding PDU shall be defined in the database.
- **signalGroup**: Signal group with SQC to be observed.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- Specified PDU object does not exist in the database.
- Given PDU or signal group does not contain a SQC signal.

## Example

```cpp
// checks the payload gaps of the message
checkId = ChkStart_SQCObservationAsrPDU (PDUToObserve, "signalGroup1");
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
