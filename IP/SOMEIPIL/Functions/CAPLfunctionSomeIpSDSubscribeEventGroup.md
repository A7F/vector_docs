# SomeIpSDSubscribeEventGroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpSDSubscribeEventGroup( dword cevgHandle, LONG tillReboot );
```

## Description

An Event Group that was unregistered at the node (consumer) using the [SomeIpSDDesubscribeEventGroup](CAPLfunctionSomeIpSDDesubscribeEventGroup.md) function can be registered again with this function. The associated Service Discovery message (Subscribe Eventgroup) is then sent.

## Parameters

- **cevgHandle**: Handle of the Consumed Event Group (see [SomeIpAddConsumedEventGroup](CAPLfunctionSomeIpAddConsumedEventGroup.md)).
- **tillReboot**:
  - 1: The TTL is set to the value **infinite** when registered. The registration of the Eventgroup (Subscribe Eventgroup) is performed once and is retained until a communication partner (producer or consumer) is restarted.
  - 0: The TTL is set to the preset value (see SomeIpSetProperty). The registration of the Event Group is sent multiple times.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
variables
{
  DWORD aep; // application endpoint handle
  DWORD csi; // consumed Service Instance handle
  DWORD ceg; // consumed Eventgroup handle
  DWORD cev; // consumed Event handle
}

on start()
{
  // open application endpoint
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
  // this function is called if the Event was sent. Parameters can be evaluated here.
}

on key 'd'
{
  SomeIpSDDesubscribeEventGroup(ceg);
  write("Event Group is no longer subscribed");
}

on key 's'
{
  SomeIpSDSubscribeEventgroup (ceg,1);
  write("Event Group will now be subscribed again");
}
```

[See Also](javascript:void(0);)
- SomeIpSDDesubscribeEventGroup
- SomeIpSDReleaseService
- SomeIpSDRequireService
- SomeIpSDSetServiceStatus
- SomeIpSDSubscribeEventGroup
