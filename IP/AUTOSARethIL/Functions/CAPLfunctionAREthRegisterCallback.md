[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthRegisterCallback.md)

CAPL Functions » Ethernet » AUTOSAR Eth IL » AREthRegisterCallback

# AREthRegisterCallback

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
LONG AREthRegisterCallback( dword objHandle, char callbackName[] );
```

## Description

Enables to register/unregister a CAPL callback function for an object which has been created separately.

## Parameters

- **objHandle**: Handle of an already existing AUTOSAR Eth IL object for which a new CAPL callback function should be registered/unregistered. The following objects and their corresponding callbacks are supported:
  - Provided events ([`<OnAREthPrepareEvent>`](CAPLfunctionOnAREthPrepareEvent.md))
  - Provided methods ([`<OnAREthMethodRequest>`](CAPLfunctionOnAREthMethodRequest.md))
  - Consumed events ([`<OnAREthEventReceived>`](CAPLfunctionOnAREthEventReceived.md))
  - Consumed fields ([`<OnAREthFieldNotification>`](CAPLfunctionOnAREthFieldNotification.md))
  - Consumed methods ([`<OnAREthMethodResponse>`](CAPLfunctionOnAREthMethodResponse.md))

- **callbackName**: The name of the new callback function to register. If a callback function was already registered, it is first unregistered and then replaced by the new one.

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
