[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthReleaseConsumedServiceInstance.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » AREthReleaseConsumedServiceInstance

# AREthReleaseConsumedServiceInstance

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
LONG AREthReleaseConsumedServiceInstance(dword csiHandle);
```

## Description

Deletes a Consumed Service Instance that was created by [AREthCreateConsumedServiceInstance](CAPLfunctionAREthCreateConsumedServiceInstance.md).

The objects assigned to the Service Instance (Eventgroups, Events, fields, and methods) are deleted when the Service Instance is closed. If the Service Instance is newly created, all objects must also be newly created.

## Parameters

- **csiHandle**: Handle of the Consumed Service Instance to be deleted.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```c
on key 'c'
{
  dword aep; // Application Endpoint handle
  dword csi; // consumed Service Instance handle

  // open an Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
  csi = AREthCreateConsumedServiceInstance(aep,10,1);

  // ... do something here

  // release the consumed Service Instance
  AREthReleaseConsumedServiceInstance(csi);

  // ... Application Endpoint can still be used here
}
```

[See Also](javascript:void(0);)
