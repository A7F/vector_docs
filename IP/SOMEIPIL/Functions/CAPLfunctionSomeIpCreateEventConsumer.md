[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpCreateEventConsumer.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpCreateEventConsumer**

# SomeIpCreateEventConsumer

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword SomeIpCreateEventConsumer(dword csiHandle, dword eventId, CHAR onEventCallback[]);
```

## Description

This function adds an Event Consumer to a Consumed Service Instance that was created by [SomeIpCreateConsumedServiceInstance](CAPLfunctionSomeIpCreateConsumedServiceInstance.md).

When a suitable Event is received, the passed Callback function is called.

An Event Consumer can be removed again using the [SomeIpRemoveEventConsumer](CAPLfunctionSomeIpRemoveEventConsumer.md) function.

## Parameters

- **csiHandle**: Handle of the Consumed Service Instance that was created with [SomeIpCreateConsumedServiceInstance](CAPLfunctionSomeIpCreateConsumedServiceInstance.md).
- **eventId**: Identifier of the Event.
- **onEventCallback**: The function name that should be called when a suitable Event is received, see [\<OnSomeIpEventReceived>\](CAPLfunctionOnSomeIpEventReceived.md).

## Return Values

- **0**: An error occurred. The error can be evaluated using the [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function.
- **>0**: Handle of the created Event Consumer.

## Example

```c
void Initialize()
{
  DWORD aep; // Application Endpoint handle
  DWORD csi; // consumed Service Instance handle
  DWORD ceg; // consumed Eventgroup handle
  DWORD cev; // consumed Event handle

  // open Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
  csi = SomeIpCreateConsumedServiceInstance(aep,10,1);

  // create Eventgroup
  ceg = SomeIpAddConsumedEventGroup(csi,1);

  // create Event Consumer
  cev = SomeIpCreateEventConsumer(csi,32770,"CallbackEvent1");
}

void CallbackEvent1(DWORD cevHandle, DWORD messageHandle)
{
  // this function is called if the Event was sent. Parameters can
  // be evaluated here.
}
```

[See Also](javascript:void(0);)