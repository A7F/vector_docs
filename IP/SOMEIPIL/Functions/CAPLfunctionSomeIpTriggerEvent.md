# SomeIpTriggerEvent

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpTriggerEvent( dword pevHandle );
```

## Description

This function triggers sending of an Event.

Afterwards, the CAPL callback function is called in [`<OnSomeIpPrepareEvent>`](CAPLfunctionOnSomeIpPrepareEvent.md), and the application has the opportunity to change or update the values of the SOME/IP Event before it is sent to its subscriber and by Multicast.

## Parameters

- **pevHandle**: Handle of the Event that is to be sent. The handle must have been created beforehand with [SomeIpAddEvent](CAPLfunctionSomeIpAddEvent.md).

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

on key 't'
{
  SomeIpTriggerEvent (pev);
}
```

[See Also](javascript:void(0);)
