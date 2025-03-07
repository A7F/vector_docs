[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthSDDesubscribeEventGroup.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthSDDesubscribeEventGroup

# AREthSDDesubscribeEventGroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthSDDesubscribeEventGroup( dword cevgHandle );
```

## Description

The Event Group is unregistered at the node (consumer). The existing subscription is terminated (Stop Subscribe Eventgroup is sent). The associated Service Discovery message (Subscribe Eventgroup) is then no longer sent by the node.

The Event Group and all assigned Events, fields, and methods are **not** deleted when unregistered.

## Parameters

- **cevgHandle**: Handle of the Consumed Event Group (see [AREthAddConsumedEventGroup](CAPLfunctionAREthAddConsumedEventGroup.md)).

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
  AREthSDDesubscribeEventGroup (ceg);
  write("Event Group is no longer subscribed");
}

on key 's'
{
  AREthSDSubscribeEventgroup(ceg,1);
  write("Event Group will now be subscribed again");
}
```

[See Also](javascript:void(0);)
```markdown
- AREthSDDesubscribeEventGroup
- AREthSDReleaseService
- AREthSDRequireService
- AREthSDSetServiceStatus
- AREthSDSubscribeEventGroup
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)