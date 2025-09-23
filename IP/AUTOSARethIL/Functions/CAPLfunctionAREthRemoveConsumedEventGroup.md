# AREthRemoveConsumedEventGroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
LONG AREthRemoveConsumedEventGroup( dword cevgHandle );
```

## Description

Removes an Event Group from a Consumed Service Instance. The Event Group was previously added by [AREthAddConsumedEventGroup](CAPLfunctionAREthAddConsumedEventGroup.md).

The Events, fields, and methods assigned to the Event Group are not deleted when the Eventgroup is closed.

## Parameters

- **cevgHandle**: Handle of the Consumed Event Group.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
on key 'c'
{
  dword aep; // Application Endpoint handle
  dword csi; // consumed Service Instance handle
  dword ceg; // consumed Eventgroup handle

  // open an Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
  csi = AREthCreateConsumedServiceInstance(aep,10,1);

  // create Eventgroup
  ceg = AREthAddConsumedEventGroup(csi,1);

  // ... do something here

  // release the consumed Service Instance
  AREthRemoveConsumedEventGroup(ceg);

  // ... Application Endpoint and provided Service Instance can still be used here
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
