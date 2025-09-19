[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkStartLinWakeupReqLengthViolation.md)

**CAPL Functions** » **Test Service Library** » **Checks** » **ChkStart_LINWakeupReqLengthViolation**

# ChkStart_LINWakeupReqLengthViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkStart_LINWakeupReqLengthViolation (duration MinLength, duration MaxLength);`
- `dword ChkStart_LINWakeupReqLengthViolation (duration MinLength, duration MaxLength, char[] CaplCallback);`

## Constructor

[TestCheck::StartLINWakeupReqLengthViolation (duration MinLength, duration MaxLength)](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::StartLINWakeupReqLengthViolation (duration MinLength, duration MaxLength);`
- `TestCheck::StartLINWakeupReqLengthViolation (duration MinLength, duration MaxLength, char[] CaplCallback);`

## Description

Checks the length of LIN wake-up request. An event will be generated if a measured length of the wake-up request is out of the specified range.

**Note**: According to the LIN specification, the wake-up request is a dominant signal in the range of a minimum of 250µs and a maximum of 5ms.

**Note**: Dependent on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **MinLength**
  - `0`: Minimum length shall not be checked
  - `>0`: Minimum allowed length
  - Unit: Can be set with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).

- **MaxLength**
  - `0`: Maximum length shall not be checked
  - `>0`: Maximum allowed length time
  - Unit: Can be set with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).

- **CaplCallback**: Name of CAPL callback function to be called on generated event. In simulation nodes, this parameter has to be set. In test modules, this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Range specified for wake-up request length is invalid
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)

## Example

```plaintext
...
dword checkId;
ChkConfig_SetPrecision(6); // switch to µs precision
// Create and start the check for LIN wake-up request
checkId = ChkStart_LINWakeupReqLengthViolation(250, 1000, "LINWakeupLenCallback");
ChkConfig_SetPrecision(3); // switch to ms precision (default)
...
// CAPL callback for violation notification
void LINWakeupLenCallback (dword aCheckId)
{
   ChkQuery_EventStatusToWrite(aCheckId);
}
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
