[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateMostErrorMessage.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_MostErrorMessage, ChkStart_MostErrorMessage

# ChkCreate_MostErrorMessage, ChkStart_MostErrorMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `dword ChkCreate_MostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aInstanceId, dword aErrorCode, Callback aCallback);`
- `dword ChkStart_MostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aInstanceId, dword aErrorCode, Callback aCallback);`
- `dword ChkCreate_MostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aErrorCode, Callback aCallback);`
- `dword ChkStart_MostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aErrorCode, Callback aCallback);`
- `dword ChkCreate_MostErrorMessage(dword aSourceDeviceAddress, dword aErrorCode, Callback aCallback);`
- `dword ChkStart_MostErrorMessage(dword aSourceDeviceAddress, dword aErrorCode, Callback aCallback);`
- `dword ChkCreate_MostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aInstanceId, dword aErrorCode);`
- `dword ChkStart_MostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aInstanceId, dword aErrorCode);`
- `dword ChkCreate_MostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aErrorCode);`
- `dword ChkStart_MostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aErrorCode);`
- `dword ChkCreate_MostErrorMessage(dword aSourceDeviceAddress, dword aErrorCode);`
- `dword ChkStart_MostErrorMessage(dword aSourceDeviceAddress, dword aErrorCode);`

## Constructor

[TestCheck::CreateMostErrorMessage](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::CreateMostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aInstanceId, dword aErrorCode, Callback aCallback);`
- `TestCheck::StartMostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aInstanceId, dword aErrorCode, Callback aCallback);`
- `TestCheck::CreateMostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aErrorCode, Callback aCallback);`
- `TestCheck::StartMostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aErrorCode, Callback aCallback);`
- `TestCheck::CreateMostErrorMessage(dword aSourceDeviceAddress, dword aErrorCode, Callback aCallback);`
- `TestCheck::StartMostErrorMessage(dword aSourceDeviceAddress, dword aErrorCode, Callback aCallback);`
- `TestCheck::CreateMostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aInstanceId, dword aErrorCode);`
- `TestCheck::StartMostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aInstanceId, dword aErrorCode);`
- `TestCheck::CreateMostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aErrorCode);`
- `TestCheck::StartMostErrorMessage(dword aSourceDeviceAddress, char[] aName, dword aErrorCode);`
- `TestCheck::CreateMostErrorMessage(dword aSourceDeviceAddress, dword aErrorCode);`
- `TestCheck::StartMostErrorMessage(dword aSourceDeviceAddress, dword aErrorCode);`

## Check Name

[MOST Error Messages (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTErrorMessages.md)

## Description

This check can be used to monitor the occurrence of MOST error messages (OpType 0xF or 0x9). The check can be implemented for a MOST device address, function block or function. In addition, monitoring can be limited to error messages with a specific error code.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aSourceDeviceAddress**: Device node address for which the occurrence of error messages is to be monitored, i.e., only those error messages with a source address equal to the value specified here are taken into consideration. Group or broadcast addresses may not be specified here.
- **aName**: Symbolic FBlock or function address for which the occurrence of error messages is to be monitored. The following formats are allowed (wildcards are not permitted):
  - "FBlock.Instance.Function"
  - "FBlock.Function"
  - "FBlock"
- **aInstance**: The instance of the FBlock specified in aName. If an instance is already specified in aName, this is overwritten by aInstance.
- **aErrorCode**: The error code that must be set in an observed error message in order for a check violation to be triggered. If 0 is specified, all error messages are monitored regardless of their error codes.
- **aCallback**: Name of the callback function to be called when an error message with the specified criteria occurs.

## Return Values

- **0**: Check was not created and may not be referenced.
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- CAPL callback does not exist.

## Example

—

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
