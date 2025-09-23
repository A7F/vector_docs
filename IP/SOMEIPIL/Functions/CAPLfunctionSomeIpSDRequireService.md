# SomeIpSDRequireService

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpSDRequireService( dword csiHandle );
```

## Description

A service that was unregistered at the node (consumer) using the [SomeIpSDReleaseService](CAPLfunctionSomeIpSDReleaseService.md) function can be registered again with this function. The associated Service Discovery message (Find Service) is then sent if necessary.

## Parameters

- **csiHandle**: Handle of the required Consumed Service Instance (see [SomeIpCreateConsumedServiceInstance](CAPLfunctionSomeIpCreateConsumedServiceInstance.md)).

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

on key 'r'
{
  SomeIpSDRequireService (csi);
}

on key 'x'
{
  SomeIpSDReleaseService(csi);
}
```

[See Also](javascript:void(0);)
