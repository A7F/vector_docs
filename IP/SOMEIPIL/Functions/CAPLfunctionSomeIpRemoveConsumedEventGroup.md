# SomeIpRemoveConsumedEventGroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
LONG SomeIpRemoveConsumedEventGroup( dword cevgHandle );
```

## Description

Removes an Event Group from a Consumed Service Instance. The Event Group was previously added by [SomeIpAddConsumedEventGroup](CAPLfunctionSomeIpAddConsumedEventGroup.md).

The Events, fields, and methods assigned to the Event Group are not deleted when the Eventgroup is closed.

## Parameters

- **cevgHandle**: Handle of the Consumed Event Group.

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

  // open an Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
  csi = SomeIpCreateConsumedServiceInstance(aep,10,1);

  // create Eventgroup
  ceg = SomeIpAddConsumedEventGroup(csi,1);

  // ... do something here

  // release the consumed Service Instance
  SomeIpRemoveConsumedEventGroup(ceg);

  // ... Application Endpoint and provided Service Instance can still be used here
}
```

**See Also**

- [SomeIpAddConsumedEventGroup](CAPLfunctionSomeIpAddConsumedEventGroup.md#aanchor18667)
- [SomeIpCallMethod](CAPLfunctionSomeIpCallMethod.md#aanchor22493)
- [SomeIpCreateConsumedServiceInstance](CAPLfunctionSomeIpCreateConsumedServiceInstance.md#aanchor6317)
- [SomeIpCreateEventConsumer](CAPLfunctionSomeIpCreateEventConsumer.md#aanchor25251)
- [SomeIpCreateFieldConsumer](CAPLfunctionSomeIpCreateFieldConsumer.md#aanchor15734)
- [SomeIpCreateMethodCall](CAPLfunctionSomeIpCreateMethodCall.md#aanchor19232)
- [SomeIpReleaseConsumedServiceInstance](CAPLfunctionSomeIpReleaseConsumedServiceInstance.md#aanchor962)
- [SomeIpRemoveConsumedEventGroup](#aanchor1721)
- [SomeIpRemoveEventConsumer](CAPLfunctionSomeIpRemoveEventConsumer.md#aanchor4282)
- [SomeIpRemoveFieldConsumer](CAPLfunctionSomeIpRemoveFieldConsumer.md#aanchor13567)
- [SomeIpRemoveMethodCall](CAPLfunctionSomeIpRemoveMethodCall.md#aanchor15404)
