[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthRemoveEventFromEventgroup.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthRemoveEventFromEventgroup

# AREthRemoveEventFromEventgroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthRemoveEventFromEventgroup( dword pevgHandle, dword pevHandle );
```

## Description

Removes an Event created by [AREthAddEvent](CAPLfunctionAREthAddEvent.md) from an Event Group which was created by [AREthAddProvidedEventGroup](CAPLfunctionAREthAddProvidedEventGroup.md). The Event itself is not deleted.

## Parameters

- **pevgHandle**: Handle of the Event Group from which an Event should be removed (see [AREthAddProvidedEventGroup](CAPLfunctionAREthAddProvidedEventGroup.md)).
- **pevHandle**: Handle of the Event that should be removed from the Event Group (see [AREthAddEvent](CAPLfunctionAREthAddEvent.md)).

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
on key 't'
{
  dword aep;  // Application Endpoint handle
  dword psi;  // provided service handle
  dword peg1; // provided Eventgroup handle
  dword peg2; // provided Eventgroup handle
  dword pev;  // provided Event handle

  // open an Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create service
  psi = AREthCreateProvidedServiceInstance(aep,10,1);

  // create Eventgroups
  peg1 = AREthAddProvidedEventGroup(psi,1);
  peg2 = AREthAddProvidedEventGroup(psi,1);

  // create Event and add Event to both Eventgroups
  pev = AREthAddEvent(psi, 1, "OnPrepareEvent1");
  AREthAddEventToEventgroup(peg1, pev);
  AREthAddEventToEventgroup(peg2, pev);

  // ensure that Event is sent cyclically
  AREthSetProperty(pev,"CycleTimeMs",1000);

  // ... do something here

  // remove Event from Eventgroup 1
  AREthRemoveEventFromEventgroup(pev);

  // ... Event is still assigned to Eventgroup 2
  // ... Application Endpoint, provided Service Instance and Eventgroup can still be used here
}
```

[See Also](javascript:void(0);)