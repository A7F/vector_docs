# AREthRemoveEvent

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthRemoveEvent(dword pevHandle);
```

## Description

Removes an Event from a Provided Service Instance. The Event was previously added by [AREthAddEvent](CAPLfunctionAREthAddEvent.md).

Afterwards, the callback registered with [AREthAddEvent](CAPLfunctionAREthAddEvent.md) is no longer called. The Event is no longer sent by the AUTOSAR Eth IL.

## Parameters

- **pevHandle**: Handle of the Event that is to be removed. The handle must have been created with [AREthAddEvent](CAPLfunctionAREthAddEvent.md).

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

  // remove the Event
  AREthRemoveEvent(pev);

  // ... Event is removed from both Eventgroups and is not sent anymore
  // ... Application Endpoint, provided Service Instance and Eventgroup can still be used here
}
```

[See Also](javascript:void(0);)
