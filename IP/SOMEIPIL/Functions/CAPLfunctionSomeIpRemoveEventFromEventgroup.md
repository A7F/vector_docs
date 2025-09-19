[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpRemoveEventFromEventgroup.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpRemoveEventFromEventgroup

# SomeIpRemoveEventFromEventgroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpRemoveEventFromEventgroup( dword pevgHandle, dword pevHandle );
```

## Description

Removes an Event created by [SomeIpAddEvent](CAPLfunctionSomeIpAddEvent.md) from an Event Group which was created by [SomeIpAddProvidedEventGroup](CAPLfunctionSomeIpAddProvidedEventGroup.md). The Event itself is not deleted.

## Parameters

- **pevgHandle**: Handle of the Event Group from which an Event should be removed (see [SomeIpAddProvidedEventGroup](CAPLfunctionSomeIpAddProvidedEventGroup.md)).
- **pevHandle**: Handle of the Event that should be removed from the Event Group (see [SomeIpAddEvent](CAPLfunctionSomeIpAddEvent.md)).

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
on key 't'
{
  DWORD aep;  // Application Endpoint handle
  DWORD psi;  // provided service handle
  DWORD peg1; // provided Eventgroup handle
  DWORD peg2; // provided Eventgroup handle
  DWORD pev;  // provided Event handle

  // open an Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create service
  psi = SomeIpCreateProvidedServiceInstance(aep,10,1);

  // create Eventgroups
  peg1 = SomeIpAddProvidedEventGroup(psi,1);
  peg2 = SomeIpAddProvidedEventGroup(psi,1);

  // create Event and add Event to both Eventgroups
  pev = SomeIpAddEvent(psi, 1, "OnPrepareEvent1");
  SomeIpAddEventToEventgroup(peg1, pev);
  SomeIpAddEventToEventgroup(peg2, pev);

  // ensure that Event is sent cyclically
  SomeIpSetProperty(pev,"CycleTimeMs",1000);

  // ... do something here

  // remove Event from Eventgroup 1
  SomeIpRemoveEventFromEventgroup(pev);

  // ... Event is still assigned to Eventgroup 2
  // ... Application Endpoint, provided Service Instance and Eventgroup can still be used here
}
```

[See Also](javascript:void(0);)
