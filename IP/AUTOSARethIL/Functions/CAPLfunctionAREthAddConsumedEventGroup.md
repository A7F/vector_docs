[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthAddConsumedEventGroup.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthAddConsumedEventGroup**

# AREthAddConsumedEventGroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword AREthAddConsumedEventGroup( dword csiHandle, dword eventGroupId );
```

## Description

This function adds an Event Group to a Consumed Service Instance that was created by [AREthCreateConsumedServiceInstance](CAPLfunctionAREthCreateConsumedServiceInstance.md).

Objects of the Event Group can be registered as follows:

- Events: [AREthCreateEventConsumer](CAPLfunctionAREthCreateEventConsumer.md)
- Fields: [AREthCreateFieldConsumer](CAPLfunctionAREthCreateFieldConsumer.md)

An Event Group can be removed again using the [AREthRemoveConsumedEventGroup](CAPLfunctionAREthRemoveConsumedEventGroup.md) function.

## Parameters

- **csiHandle**: Handle of the Consumed Service Instance.
- **eventGroupId**: Identifier of the Event Group.

## Return Values

- **0**: An error occurred. The error can be evaluated using the [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function.
- **>0**: Handle of the created Consumed Event Group.

## Example

```plaintext
void Initialize()
{
  dword aep; // application endpoint handle
  dword csi; // consumed Service Instance handle
  dword ceg; // consumed Eventgroup handle
  dword cev; // consumed Event handle

  // open application endpoint
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