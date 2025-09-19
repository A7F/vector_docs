[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthCreateEventConsumer.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » AREthCreateEventConsumer

# AREthCreateEventConsumer

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword AREthCreateEventConsumer( dword csiHandle, dword eventId, CHAR onEventCallback[]);
```

## Description

This function adds an Event Consumer to a Consumed Service Instance that was created by [AREthCreateConsumedServiceInstance](CAPLfunctionAREthCreateConsumedServiceInstance.md).

When a suitable Event is received, the passed Callback function is called.

An Event Consumer can be removed again using the [AREthRemoveEventConsumer](CAPLfunctionAREthRemoveEventConsumer.md) function.

## Parameters

- **csiHandle**: Handle of the Consumed Service Instance that was created with [AREthCreateConsumedServiceInstance](CAPLfunctionAREthCreateConsumedServiceInstance.md).
- **eventId**: Identifier of the Event.
- **onEventCallback**: The function name that should be called when a suitable Event is received, see [`<OnAREthEventReceived>`](CAPLfunctionOnAREthEventReceived.md).

## Return Values

- **0**: An error occurred. The error can be evaluated using the [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function.
- **>0**: Handle of the created Event Consumer.

## Example

```plaintext
void Initialize()
{
  dword aep; // Application Endpoint handle
  dword csi; // consumed Service Instance handle
  dword ceg; // consumed Eventgroup handle
  dword cev; // consumed Event handle

  // open Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
  csi = AREthCreateConsumedServiceInstance(aep,10,1);

  // create Eventgroup
  ceg = AREthAddConsumedEventGroup(csi,1);

  // create Event Consumer
  cev = AREthCreateEventConsumer(csi,1,"CallbackEvent1");
}

void CallbackEvent1(dword cevHandle, dword messageHandle)
{
  // this function is called if the Event was sent. Parameters can
  // be evaluated here.
}
```

[See Also](javascript:void(0);)
- AREthAddConsumedEventGroup
- AREthCallMethod
- AREthCreateConsumedServiceInstance
- AREthCreateEventConsumer
- AREthCreateFieldConsumer
- AREthCreateMethodCall
- AREthReleaseConsumedServiceInstance
- AREthRemoveConsumedEventGroup
- AREthRemoveEventConsumer
- AREthRemoveFieldConsumer
- AREthRemoveMethodCall

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
