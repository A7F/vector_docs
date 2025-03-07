[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateErrorFramesOccured.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_ErrorFramesOccured, ChkStart_ErrorFramesOccured

# ChkCreate_ErrorFramesOccured, ChkStart_ErrorFramesOccured

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_ErrorFramesOccured (long MinCountOfErrorFrames, long MaxCountOfErrorFrames, dword Timeout, char CaplCallbackFunction[]);`
- `dword ChkStart_ErrorFramesOccured (long MinCountOfErrorFrames, long MaxCountOfErrorFrames, dword Timeout, char CaplCallbackFunction[]);`
- `dword ChkCreate_ErrorFramesOccured (char CaplCallbackFunction[]);`
- `dword ChkStart_ErrorFramesOccured (char CaplCallbackFunction[]);`
- `dword ChkCreate_ErrorFramesOccured (long MinCountOfErrorFrames, long MaxCountOfErrorFrames, dword Timeout);`
- `dword ChkStart_ErrorFramesOccured (long MinCountOfErrorFrames, long MaxCountOfErrorFrames, dword Timeout);`
- `dword ChkCreate_ErrorFramesOccured ();`
- `dword ChkStart_ErrorFramesOccured ();`

## Constructor

- `TestCheck::CreateErrorFramesOccured (long MinCountOfErrorFrames, long MaxCountOfErrorFrames, dword Timeout, char CaplCallbackFunction[]);`
- `TestCheck::StartErrorFramesOccured (long MinCountOfErrorFrames, long MaxCountOfErrorFrames, dword Timeout, char CaplCallbackFunction[]);`
- `TestCheck::CreateErrorFramesOccured (char CaplCallbackFunction[]);`
- `TestCheck::StartErrorFramesOccured (char CaplCallbackFunction[]);`
- `TestCheck::CreateErrorFramesOccured (long MinCountOfErrorFrames, long MaxCountOfErrorFrames, dword Timeout);`
- `TestCheck::StartErrorFramesOccured (long MinCountOfErrorFrames, long MaxCountOfErrorFrames, dword Timeout);`
- `TestCheck::CreateErrorFramesOccured ();`
- `TestCheck::StartErrorFramesOccured ();`

## Check Name

[Error Frame Count](../../../TestCommands/CheckDescriptions/CDErrorFrameCount.md)

## Description

Checks the occurrence of Error Frames on the bus. The event is generated if fewer than **MinCountOfErrorFrames** or more than **MaxCountOfErrorFrames** are received.

The minimum condition is only checked when 'Timeout != 0'

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **MinCountOfErrorFrames**: Minimum number of Error Frames that must be received. This parameter is set to 0 in signatures without parameter. Only check when 'Timeout != 0'
- **MaxCountOfErrorFrames**: Maximum number of Error Frames that may occur. This parameter is set to 0 in signatures without parameter.
- **Timeout**: The check is automatically stopped after this time. The check is no longer in progress. If the timeout is specified with zero, it behaves like all other checks. It runs until the [ChkControl_Stop(id)](CAPLfunctionChkControlStop.md) function is called. Default unit [ms], if not changed with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).
- **CaplCallbackFunction**: In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- MinCountOfErrorFrames > MaxCountOfErrorFrames
- CAPL callback does not exist

## Example

```c
// observes that less than 3 Error Frames occurs
checkId = ChkStart_ErrorFramesOccured (0, 2, 0);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)