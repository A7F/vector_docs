[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpCreateConsumedServiceInstance.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpCreateConsumedServiceInstance

# SomeIpCreateConsumedServiceInstance

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword SomeIpCreateConsumedServiceInstance( dword aepHandle, dword serviceId, dword instanceId ); // form 1
dword SomeIpCreateConsumedServiceInstance( dword aepHandle, dword serviceId, dword instanceId, dword majorVersion, dword minorVersion ); // form 2
```

## Description

This function creates a Consumed Service Instance and adds it to an Application Endpoint which was created by [SomeIpOpenLocalApplicationEndpoint](CAPLfunctionSomeIpOpenLocalApplicationEndpoint.md).

Form 2 tries to find and use a specific version of the provided service instance. Form 1 uses version 1.

Objects can be assigned to the Service Instance as follows:

- Event Groups: [SomeIpAddConsumedEventGroup](CAPLfunctionSomeIpAddConsumedEventGroup.md)
- Events: [SomeIpCreateEventConsumer](CAPLfunctionSomeIpCreateEventConsumer.md)
- Fields: [SomeIpCreateFieldConsumer](CAPLfunctionSomeIpCreateFieldConsumer.md)
- Methods: [SomeIpCreateMethodCall](CAPLfunctionSomeIpCreateMethodCall.md)

[SomeIpReleaseConsumedServiceInstance](CAPLfunctionSomeIpReleaseConsumedServiceInstance.md) can be used to delete the Service Instance again.

## Parameters

- **aepHandle**: Handle of the Application Endpoint.
- **serviceId**: Service identifier
- **instanceId**: Instance identifier
- **majorVersion**: Service interface major version.
- **minorVersion**: Service interface minor version.

## Return Values

- **0**: An error occurred. The error can be evaluated using the [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function.
- **>0**: Handle of the created Consumed Service Instance.

## Example

```plaintext
void Initialize()
{
  DWORD aep; // application endpoint handle
  DWORD csi; // consumed Service Instance handle
  DWORD ceg; // consumed Eventgroup handle
  DWORD cev; // consumed Event handle

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
  // this function is called if the Event was sent. Parameters can
  // be evaluated here.
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)