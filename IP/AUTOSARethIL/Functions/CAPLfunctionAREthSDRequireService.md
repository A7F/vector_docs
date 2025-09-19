[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthSDRequireService.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthSDRequireService

# AREthSDRequireService

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthSDRequireService( dword csiHandle );
```

## Description

A service that was unregistered at the node (consumer) using the [AREthSDReleaseService](CAPLfunctionAREthSDReleaseService.md) function can be registered again with this function. The associated Service Discovery message (Find Service) is then sent if necessary.

## Parameters

- **csiHandle**: Handle of the required Consumed Service Instance (see [AREthCreateConsumedServiceInstance](CAPLfunctionAREthCreateConsumedServiceInstance.md)).

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

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
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);
  // create Service Instance
  csi = AREthCreateConsumedServiceInstance(aep,10,1);
  // create Eventgroup
  ceg = AREthAddConsumedEventGroup(csi,1);
  // create Event Consumer
  cev = AREthCreateEventConsumer(csi,1,"CallbackEvent1");
}

void CallbackEvent1(DWORD cevHandle, DWORD messageHandle)
{
  // this function is called if the Event was sent. Parameters can be evaluated here.
}

on key 'r'
{
  AREthSDRequireService (csi);
}

on key 'x'
{
  AREthSDReleaseService(csi);
}
```

[See Also](javascript:void(0);)
- AREthSDDesubscribeEventGroup
- [AREthSDReleaseService](CAPLfunctionAREthSDReleaseService.md#aanchor14012)
- AREthSDRequireService
- [AREthSDSetServiceStatus](CAPLfunctionAREthSDSetServiceStatus.md#aanchor28236)
- [AREthSDSubscribeEventGroup](CAPLfunctionAREthSDSubscribeEventGroup.md#aanchor24988)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
