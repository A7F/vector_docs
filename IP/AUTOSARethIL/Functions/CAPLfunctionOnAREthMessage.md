[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionOnAREthMessage.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **OnAREthMessage**

# OnAREthMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void OnAREthMessage( dword messageHandle );
```

## Description

This callback function can be implemented in the CAPL program to be notified when a SOME/IP message is received.

The function is called for all those SOME/IP messages that are received on the local Application Endpoint of the IL, see [AREthOpenLocalApplicationEndpoint](CAPLfunctionAREthOpenLocalApplicationEndpoint.md).

## Parameters

- **messageHandle**: Handle of the received SOME/IP message. The handle is needed for the functions that read out message data.

## Return Values

—

## Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)