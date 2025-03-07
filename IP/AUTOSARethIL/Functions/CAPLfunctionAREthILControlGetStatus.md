[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthILControlGetStatus.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » AREthILControlGetStatus

# AREthILControlGetStatus

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthILControlGetStatus();
```

## Description

Returns current status of AUTOSAR Eth IL.

## Parameters

—

## Return Values

- **0**: uninitialized
- **1**: initialized autostart allowed
- **2**: initialized no autostart
- **3**: initialized no autostart after prestart
- **4**: active
- **5**: stopped; suspended
- **6**: measurement stopping
- **7**: measurement ended

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)