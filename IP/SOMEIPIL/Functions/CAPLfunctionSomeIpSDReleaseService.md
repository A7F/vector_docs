# SomeIpSDReleaseService

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpSDReleaseService( dword csiHandle );
```

## Description

The service is unregistered at the node (consumer). The associated Service Discovery message (Find Service) is then no longer sent by the node.

The Service Instance and all assigned Eventgroups, Events, Fields, and Methods are **not** deleted when the Service Instance is unregistered.

## Parameters

- **csiHandle**: Handle of the Consumed Service Instance to be released (see [SomeIpCreateConsumedServiceInstance](CAPLfunctionSomeIpCreateConsumedServiceInstance.md)).

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
  SomeIpSDReleaseService (csi);
}
```

[See Also](javascript:void(0);)
