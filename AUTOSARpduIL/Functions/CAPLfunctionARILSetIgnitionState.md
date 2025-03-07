[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AUTOSARpduIL/Functions/CAPLfunctionARILSetIgnitionState.md)

**CAPL Functions** » [AUTOSAR PDU IL](../CAPLfunctionsAUTOSARpduILOverview.md) » ARILSetIgnitionState

# ARILSetIgnitionState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Note

Setting the ignition state with this function will also update the appropriate global system variable (`sysvar::_ILControl::Ignition`). Therefore the state in all ILs will automatically be set accordingly.

## Function Syntax

```plaintext
long ARILSetIgnitionState (long value);
```

## Description

Activates or deactivates the ignition status globally.

## Parameters

- **value**
  - 0: Set ignition state **off**.
  - 1: Set ignition state **on**.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)