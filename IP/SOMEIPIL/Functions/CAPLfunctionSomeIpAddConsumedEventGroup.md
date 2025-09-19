[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpAddConsumedEventGroup.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpAddConsumedEventGroup**

# SomeIpAddConsumedEventGroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword SomeIpAddConsumedEventGroup( dword csiHandle, dword eventGroupId );
```

## Description

This function adds an Event Group to a Consumed Service Instance that was created by [SomeIpCreateConsumedServiceInstance](CAPLfunctionSomeIpCreateConsumedServiceInstance.md).

Objects of the Event Group can be registered as follows:

- Events: [SomeIpCreateEventConsumer](CAPLfunctionSomeIpCreateEventConsumer.md)
- Fields: [SomeIpCreateFieldConsumer](CAPLfunctionSomeIpCreateFieldConsumer.md)

An Event Group can be removed again using the [SomeIpRemoveConsumedEventGroup](CAPLfunctionSomeIpRemoveConsumedEventGroup.md) function.

## Parameters

- **csiHandle**: Handle of the Consumed Service Instance.
- **eventGroupId**: Identifier of the Event Group.

## Return Values

- **0**: An error occurred. The error can be evaluated using the [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function.

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

[See Also](javascript:void(0);)

```markdown
- [SomeIpAddConsumedEventGroup](#aanchor18667)
- [SomeIpCallMethod](CAPLfunctionSomeIpCallMethod.md#aanchor22493)
- [SomeIpCreateConsumedServiceInstance](CAPLfunctionSomeIpCreateConsumedServiceInstance.md#aanchor6317)
- [SomeIpCreateEventConsumer](CAPLfunctionSomeIpCreateEventConsumer.md#aanchor25251)
- [SomeIpCreateFieldConsumer](CAPLfunctionSomeIpCreateFieldConsumer.md#aanchor15734)
- [SomeIpCreateMethodCall](CAPLfunctionSomeIpCreateMethodCall.md#aanchor19232)
- [SomeIpReleaseConsumedServiceInstance](CAPLfunctionSomeIpReleaseConsumedServiceInstance.md#aanchor962)
- [SomeIpRemoveConsumedEventGroup](CAPLfunctionSomeIpRemoveConsumedEventGroup.md#aanchor1721)
- [SomeIpRemoveEventConsumer](CAPLfunctionSomeIpRemoveEventConsumer.md#aanchor4282)
- [SomeIpRemoveFieldConsumer](CAPLfunctionSomeIpRemoveFieldConsumer.md#aanchor13567)
- [SomeIpRemoveMethodCall](CAPLfunctionSomeIpRemoveMethodCall.md#aanchor15404)
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
