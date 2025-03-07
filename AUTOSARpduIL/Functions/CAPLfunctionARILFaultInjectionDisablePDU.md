[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AUTOSARpduIL/Functions/CAPLfunctionARILFaultInjectionDisablePDU.md)

**CAPL Functions** » **AUTOSAR PDU IL** » **ARILFaultInjectionDisablePDU**

# ARILFaultInjectionDisablePDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILFaultInjectionDisablePDU (dbMsg);
```

## Description

Disables the sending of the PDU except by calling the function [ARILSetPDUEvent](CAPLfunctionARILSetPDUEvent.md).

## Parameters

- **dbMsg**: The symbolic name of a PDU in the database.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)