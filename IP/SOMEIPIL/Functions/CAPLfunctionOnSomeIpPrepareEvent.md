[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionOnSomeIpPrepareEvent.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » `<OnSomeIpPrepareEvent>`

# `<OnSomeIpPrepareEvent>`

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void <OnSomeIpPrepareEvent>( dword pevHandle, dword messageHandle );
```

## Description

A callback function with this signature must be passed to the CAPL function [SomeIpAddEvent](CAPLfunctionSomeIpAddEvent.md).

The callback is called before sending. The values of the SOME/IP message can be changed or updated before sending.

## Parameters

- **pevHandle**: Handle of the Event that triggered the callback.
- **messageHandle**: Message handle of the SOME/IP request.

## Return Values

—

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
  pev = SomeIpAddEvent(psi, 1, "OnPrepareEvent1 ");
  SomeIpAddEventToEventgroup(peg, pev);
  // ensure that Event is sent cyclically
  SomeIpSetProperty(pev,"CycleTimeMs",1000);
}

void OnPrepareEvent1 (DWORD eventHandle, DWORD messageHandle)
{
  // this function is called before the Event is sent. Parameters can be specified here.
}
```

[See Also](javascript:void(0);)
