[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkStartLinRespErrorSignal.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkStart_LINRespErrorSignal

# ChkStart_LINRespErrorSignal

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkStart_LINRespErrorSignal (Node ObservedNode);`
- `dword ChkStart_LINRespErrorSignal ();`
- `dword ChkStart_LINRespErrorSignal ( Node ObservedNode, char[] CaplCallback);`
- `dword ChkStart_LINRespErrorSignal (char[] CaplCallback);`

## [Constructor](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::StartLINRespErrorSignal (Node ObservedNode);`
- `TestCheck::StartLINRespErrorSignal ();`
- `TestCheck::StartLINRespErrorSignal ( Node ObservedNode, char[] CaplCallback);`
- `TestCheck::StartLINRespErrorSignal (char[] CaplCallback);`

## Description

Checks the LIN Response_Error signal for a specified LIN Slave node or for all LIN nodes. An event will be generated, if the Response_Error signal value changes from FALSE (0) to TRUE (1). J2602 specific: Bit 7 of Status Byte serves as Response_Error signal.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **ObservedNode**: Node to be checked. Only Slave nodes are allowed.
- **CaplCallback**: Name of CAPL callback function to be called on generated event. In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- The specified node is Master
- The Response_Error signal for the specified node is not defined or the signal is not defined for any Slave node
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)
- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventNodeName](CAPLfunctionChkQueryEventNodeName.md)

## Example

```plaintext
...
dword checkId;
// Create and start the check for LIN response_error signal
checkId = ChkStart_LINRespErrorSignal("LINRespErrCallback");
...
// CAPL callback for violation notification
void LINRespErrCallback (dword aCheckId)
{
   ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
