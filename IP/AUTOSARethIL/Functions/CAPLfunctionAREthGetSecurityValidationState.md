[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthGetSecurityValidationState.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » AREthGetSecurityValidationState

# AREthGetSecurityValidationState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthGetSecurityValidationState ( dword messageHandle );
```

## Description

This function returns the Security-Validation-State of a received SOME/IP message.

## Parameters

- **messageHandle**: Handle of a received SOME/IP message (e.g. see [OnAREthMessage](CAPLfunctionOnAREthMessage.md))

## Return Values

- **-1**: Message is invalid
- **0**: Message is not secured
- **1**: Message is valid
- **>1**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
