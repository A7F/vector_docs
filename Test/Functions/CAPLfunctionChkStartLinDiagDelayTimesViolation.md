[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkStartLinDiagDelayTimesViolation.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkStart_LINDiagDelayTimesViolation

# ChkStart_LINDiagDelayTimesViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkStart_LINDiagDelayTimesViolation (Node ObservedNode);`
- `dword ChkStart_LINDiagDelayTimesViolation ();`
- `dword ChkStart_LINDiagDelayTimesViolation(Node ObservedNode, char[] CaplCallback);`
- `dword ChkStart_LINDiagDelayTimesViolation(char[] CaplCallback);`

## Constructor

[TestCheck::StartLINDiagDelayTimesViolation (Node ObservedNode)](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::StartLINDiagDelayTimesViolation ();`
- `TestCheck::StartLINDiagDelayTimesViolation(Node ObservedNode, char[] CaplCallback);`
- `TestCheck::StartLINDiagDelayTimesViolation(char[] CaplCallback);`

## Description

Checks the values of P2_min and ST_min for a specified LIN Slave node or for all LIN Slaves defined in LDF. An event will be generated, if the measured P2_min or ST_min value is smaller than one specified in the database (LDF).

**Note**: The check monitors bus traffic and automatically recognizes diagnostic frames.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **ObservedNode**: Slave node to be checked.
- **CaplCallback**: Name of CAPL callback function to be called on generated event. In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- The specified node is Master
- Specified node does not appear under "Node Attributes" section in LDF or P2_min, ST_min are not defined
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventReason](CAPLfunctionChkQueryEventReason.md)
- [ChkQuery_EventNodeName](CAPLfunctionChkQueryEventNodeName.md)

## Example

```plaintext
...
dword checkId;
// Create and start the check for LIN diagnostic delay times
checkId = ChkStart_LINDiagDelayTimesViolation("LINDiagDelayTimesCallback"); 
...
// CAPL callback for violation notification
void LINDiagDelayTimesCallback (dword aCheckId)
{   ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
