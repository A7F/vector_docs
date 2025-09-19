[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionA664SetFunctionalStatus.md)

## A664SetFunctionalStatus

**CAPL Functions** » AFDX » A664SetFunctionalStatus

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
long A664SetFunctionalStatus (PDU aPDU, BYTE fs)
```

### Description

This function sets the Functional Status (FS) of a AFDX-PDU (FDS).

**Note:** This function is only available in PDU-mode.

### Parameters

- **aPDU**: The AFDX-PDU (FDS) which status should be set.
- **fs**: The 8-bit value which should be applied.

### Return Values

- **0**: A valid FS was successfully set.
- **1**: The value was set but is not conform with the A664-P7-specification.

### Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
