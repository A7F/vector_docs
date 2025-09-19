[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthSDSubscribeEventGroup.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » AREthSDSubscribeEventGroup

# AREthSDSubscribeEventGroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthSDSubscribeEventGroup( dword cevgHandle, LONG tillReboot );
```

## Description

An Event Group that was unregistered at the node (consumer) using the [AREthSDDesubscribeEventGroup](CAPLfunctionAREthSDDesubscribeEventGroup.md) function can be registered again with this function. The associated Service Discovery message (Subscribe Eventgroup) is then sent.

## Parameters

- **cevgHandle**: Handle of the Consumed Event Group (see [AREthAddConsumedEventGroup](CAPLfunctionAREthAddConsumedEventGroup.md)).
  
- **tillReboot**:
  - 1: The TTL is set to the value **infinite** when registered. The registration of the Eventgroup (Subscribe Eventgroup) is performed once and is retained until a communication partner (producer or consumer) is restarted.
  - 0: The TTL is set to the preset value (see AREthSetProperty). The registration of the Event Group is sent multiple times.

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

on key 'd'
{
  AREthSDDesubscribeEventGroup(ceg);
  write("Event Group is no longer subscribed");
}

on key 's'
{
  AREthSDSubscribeEventgroup (ceg,1);
  write("Event Group will now be subscribed again");
}
```

[See Also](javascript:void(0);)

```markdown
- [AREthSDDesubscribeEventGroup](CAPLfunctionAREthSDDesubscribeEventGroup.md#aanchor20104)
- [AREthSDReleaseService](CAPLfunctionAREthSDReleaseService.md#aanchor14012)
- [AREthSDRequireService](CAPLfunctionAREthSDRequireService.md#aanchor3056)
- [AREthSDSetServiceStatus](CAPLfunctionAREthSDSetServiceStatus.md#aanchor28236)
- [AREthSDSubscribeEventGroup](#aanchor24988)
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
