# SomeIpRemoveEventConsumer

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword SomeIpRemoveEventConsumer( dword cevHandle );
```

## Description

Removes an Event from a Consumed Service Instance. The Event was previously added by [SomeIpCreateEventConsumer](CAPLfunctionSomeIpCreateEventConsumer.md).

Afterwards, the callback registered with [SomeIpCreateEventConsumer](CAPLfunctionSomeIpCreateEventConsumer.md) is no longer called.

## Parameters

- **cevHandle**: Handle of the Event to be removed (see [SomeIpCreateEventConsumer](CAPLfunctionSomeIpCreateEventConsumer.md)).

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
on key 'c'
{
  DWORD aep; // Application Endpoint handle
  DWORD csi; // consumed Service Instance handle
  DWORD ceg; // consumed Eventgroup handle
  DWORD cev; // consumed Event handle

  // open an Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
  csi = SomeIpCreateConsumedServiceInstance(aep,10,1);

  // create Eventgroup
  ceg = SomeIpAddConsumedEventGroup(csi,1);

  // create Event Consumer
  cev = SomeIpCreateEventConsumer(csi,32770,"CallbackEventA1");

  // ... do something here

  // release the consumed Service Instance
  SomeIpRemoveEventConsumer(cev);

  // ... Application Endpoint, provided Service Instance and consumed Eventgroup can still be used here
}
```

[See Also](javascript:void(0);)
