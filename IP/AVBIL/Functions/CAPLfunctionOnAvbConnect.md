[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionOnAvbConnect.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **OnAvbConnect**

# OnAvbConnect

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnAvbConnect(dword talkerHandle, dword result);
```

## Description

This callback is dispatched when an asynchronous connection operation completes.

## Parameters

- **talkerHandle**: The Talker handle.
- **result**: The specific result code of the operation. If the operation completed successfully the value is zero. Otherwise the value is non-zero.

## Return Values

—

## Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
