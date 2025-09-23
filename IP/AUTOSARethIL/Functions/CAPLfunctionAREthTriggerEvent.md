# AREthTriggerEvent

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthTriggerEvent( dword pevHandle );
```

## Description

This function triggers sending of an Event.

Afterwards, the CAPL callback function is called in [`<OnAREthPrepareEvent>`](CAPLfunctionOnAREthPrepareEvent.md), and the application has the opportunity to change or update the values of the SOME/IP Event before it is sent to its subscriber and by Multicast.

## Parameters

- **pevHandle**: Handle of the Event that is to be sent. The handle must have been created beforehand with [AREthAddEvent](CAPLfunctionAREthAddEvent.md).

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

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
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);
  // create Service Instance
  psi = AREthCreateProvidedServiceInstance(aep,10,1);
  // create Eventgroup
  peg = AREthAddProvidedEventGroup(psi,1);
  // create Event and add Event to Eventgroup
  pev = AREthAddEvent(psi, 1, "OnPrepareEvent1");
  SomeIpAddEventToEventgroup(peg, pev);
  // ensure that Event is sent cyclically
  AREthSetProperty(pev,"CycleTimeMs",1000);
}

void OnPrepareEvent1(DWORD eventHandle, DWORD messageHandle)
{
  // this function is called before the Event is sent. Parameters can be specified here.
}

on key 't'
{
  AREthTriggerEvent (pev);
}
```

[See Also](javascript:void(0);)
