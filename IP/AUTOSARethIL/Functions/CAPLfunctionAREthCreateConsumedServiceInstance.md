# AREthCreateConsumedServiceInstance

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword AREthCreateConsumedServiceInstance( dword aepHandle, dword serviceId, dword instanceId ); // form 1
dword AREthCreateConsumedServiceInstance( dword aepHandle, dword serviceId, dword instanceId, dword majorVersion, dword minorVersion); // form 2
```

## Description

This function creates a Consumed Service Instance and adds it to an Application Endpoint which was created by [AREthOpenLocalApplicationEndpoint](CAPLfunctionAREthOpenLocalApplicationEndpoint.md).

Form 2 tries to find and use a specific version of the provided service instance. Form 1 uses version 1.

Objects can be assigned to the Service Instance as follows:

- Event Groups: [AREthAddConsumedEventGroup](CAPLfunctionAREthAddConsumedEventGroup.md)
- Events: [AREthCreateEventConsumer](CAPLfunctionAREthCreateEventConsumer.md)
- Fields: [AREthCreateFieldConsumer](CAPLfunctionAREthCreateFieldConsumer.md)
- Methods: [AREthCreateMethodCall](CAPLfunctionAREthCreateMethodCall.md)

[AREthReleaseConsumedServiceInstance](CAPLfunctionAREthReleaseConsumedServiceInstance.md) can be used to delete the Service Instance again.

## Parameters

- **aepHandle**: Handle of the Application Endpoint.
- **serviceId**: Service identifier
- **instanceId**: Instance identifier
- **majorVersion**: Service interface major version.
- **minorVersion**: Service interface minor version.

## Return Values

- **0**: An error occurred. The error can be evaluated using the [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function.
- **>0**: Handle of the created Consumed Service Instance.

## Example

```c
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
