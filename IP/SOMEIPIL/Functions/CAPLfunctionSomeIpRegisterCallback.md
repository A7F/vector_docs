[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpRegisterCallback.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpRegisterCallback**

# SomeIpRegisterCallback

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
LONG SomeIpRegisterCallback( dword objHandle, char callbackName[] );
```

## Description

Enables to register/unregister a CAPL callback function for an object which has been created separately.

## Parameters

- **objHandle**  
  Handle of an already existing SOME/IP IL object for which a new CAPL callback function should be registered/unregistered. The following objects and their corresponding callbacks are supported:
  - Provided events ([OnSomeIpPrepareEvent](CAPLfunctionOnSomeIpPrepareEvent.md))
  - Provided methods ([OnSomeIpMethodRequest](CAPLfunctionOnSomeIpMethodRequest.md))
  - Consumed events ([OnSomeIpEventReceived](CAPLfunctionOnSomeIpEventReceived.md))
  - Consumed fields ([OnSomeIpFieldNotification](CAPLfunctionOnSomeIpFieldNotification.md))
  - Consumed methods ([OnSomeIpMethodResponse](CAPLfunctionOnSomeIpMethodResponse.md))

- **callbackName**  
  The name of the new callback function to register. If a callback function was already registered, it is first unregistered and then replaced by the new one.

## Return Values

- **0**  
  The function was successfully executed.

- **>0**  
  [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)