[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AUTOSARpduIL/Functions/CAPLfunctionARILFaultInjectionResetPDULength.md)

**CAPL Functions** » **AUTOSAR PDU IL** » **ARILFaultInjectionResetPDULength**

# ARILFaultInjectionResetPDULength

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILFaultInjectionResetPDULength (dbMsg dbMessage);
```

## Description

Resets the payload length back to its original value from the database.

## Parameters

- **dbMessage**: The symbolic name of a PDU in the database.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)