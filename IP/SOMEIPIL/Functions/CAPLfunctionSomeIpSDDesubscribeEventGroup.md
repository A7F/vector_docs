[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpSDDesubscribeEventGroup.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpSDDesubscribeEventGroup

# SomeIpSDDesubscribeEventGroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpSDDesubscribeEventGroup( dword cevgHandle );
```

## Description

The Event Group is unregistered at the node (consumer). The existing subscription is terminated (Stop Subscribe Eventgroup is sent). The associated Service Discovery message (Subscribe Eventgroup) is then no longer sent by the node.

The Event Group and all assigned Events, fields, and methods are **not** deleted when unregistered.

## Parameters

- **cevgHandle**: Handle of the Consumed Event Group (see [SomeIpAddConsumedEventGroup](CAPLfunctionSomeIpAddConsumedEventGroup.md)).

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

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
  // this function is called if the Event was sent. Parameters can be evaluated here.
}

on key 'd'
{
  SomeIpSDDesubscribeEventGroup (ceg);
  write("Event Group is no longer subscribed");
}

on key 's'
{
  SomeIpSDSubscribeEventgroup(ceg,1);
  write("Event Group will now be subscribed again");
}
```

[See Also](javascript:void(0);)
```markdown
- SomeIpSDDesubscribeEventGroup
- [SomeIpSDReleaseService](CAPLfunctionSomeIpSDReleaseService.md#aanchor27015)
- [SomeIpSDRequireService](CAPLfunctionSomeIpSDRequireService.md#aanchor7892)
- [SomeIpSDSetServiceStatus](CAPLfunctionSomeIpSDSetServiceStatus.md#aanchor8955)
- [SomeIpSDSubscribeEventGroup](CAPLfunctionSomeIpSDSubscribeEventGroup.md#aanchor30613)
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)