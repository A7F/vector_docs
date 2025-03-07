[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpRemoveFieldFromEventgroup.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpRemoveFieldFromEventgroup

# SomeIpRemoveFieldFromEventgroup

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpRemoveFieldFromEventgroup( dword pevgHandle, dword pfHandle );
```

## Description

Removes a field created by [SomeIpAddField](CAPLfunctionSomeIpAddField.md) from an Event Group which was created by [SomeIpAddProvidedEventGroup](CAPLfunctionSomeIpAddProvidedEventGroup.md). The field itself is **not** deleted.

## Parameters

- **pevgHandle**: Handle of the Event Group from which a field should be removed (see [SomeIpAddProvidedEventGroup](CAPLfunctionSomeIpAddProvidedEventGroup.md)).
- **pfHandle**: Handle of the field that should be removed from the Event Group (see [SomeIpAddField](CAPLfunctionSomeIpAddField.md)).

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
variables
{
  DWORD aep; // Application Endpoint handle
  DWORD psi; // provided service handle
  DWORD peg; // provided Eventgroup handle
  DWORD pev; // provided Event handle
}

on start()
{
  // open Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);
  // create Service Instance
  psi = SomeIpCreateProvidedServiceInstance(aep,10,1);
  // create Eventgroup
  peg = SomeIpAddProvidedEventGroup(psi,1);
  // create Event and add Event to Eventgroup
  pev = SomeIpAddEvent(psi, 1, "OnPrepareEvent1");
  SomeIpAddEventToEventgroup(peg, pev);
  // ensure that Event is sent cyclically
  SomeIpSetProperty(pev,"CycleTimeMs",1000);
}

void OnPrepareEvent1(DWORD eventHandle, DWORD messageHandle)
{
  // this function is called before the Event is sent. Parameters can be specified here.
}

on key 'r'
{
  SomeIpRemoveFieldFromEventGroup (peg, pev);
}
```

[See Also](javascript:void(0);)