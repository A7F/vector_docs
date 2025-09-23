[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkStartLinRespToleranceViolation.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkStart_LINRespToleranceViolation

# ChkStart_LINRespToleranceViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkStart_LINRespToleranceViolation (Message Frame, float Tolerance);`
- `dword ChkStart_LINRespToleranceViolation (Node ObservedNode, float Tolerance);`
- `dword ChkStart_LINRespToleranceViolation (Message Frame, float Tolerance, char[] CaplCallback);`
- `dword ChkStart_LINRespToleranceViolation (Node ObservedNode, float Tolerance, char[] CaplCallback);`

## Constructor

[TestCheck::StartLINRespToleranceViolation (Message Frame, float Tolerance)](../../../Shared/CAPL/General/ClassesAndObjects.md)
- `TestCheck::StartLINRespToleranceViolation (Node ObservedNode, float Tolerance);`
- `TestCheck::StartLINRespToleranceViolation (Message Frame, float Tolerance, char[] CaplCallback);`
- `TestCheck::StartLINRespToleranceViolation (Node ObservedNode, float Tolerance, char[] CaplCallback);`

## Description

Checks the LIN response transmission time. An event will be generated if the measured response transmission time is over the allowed tolerance.

**Note**
- This function monitors frames transmitted without a failure only.
- Components influencing response tolerance: inter-byte space, response space.
- For LIN 2.0 compliance, the Tolerance has to be in the range [0 .. 40]%.

## Parameters

- **Frame**: Unconditional LIN frame to verify.
- **ObservedNode**: Node, whose published frames shall be verified.
- **CaplCallback**: Name of CAPL callback function to be called on generated event. In simulation nodes, this parameter has to be set. In test modules, this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced.
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Check-specific Queries

- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)
- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventNodeName](CAPLfunctionChkQueryEventNodeName.md)
- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventTiming](CAPLfunctionChkQueryEventTiming.md)

## Example

```plaintext
...
dword checkId;
ChkConfig_SetPrecision(9); // switch to ns precision
// Create and start the check for LIN response tolerance violation in "Motor1" node
checkId = ChkStart_LINRespToleranceViolation(LIN20db::Motor1, 40.0 , "LINRespToleranceCallback");
ChkConfig_SetPrecision(3); // switch to ms precision (default)
...
// CAPL callback for violation notification
void LINRespToleranceCallback (dword aCheckId)
{
   ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
