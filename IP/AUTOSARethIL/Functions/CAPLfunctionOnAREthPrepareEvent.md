[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionOnAREthPrepareEvent.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » `<OnAREthPrepareEvent>`

# `<OnAREthPrepareEvent>`

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void <OnAREthPrepareEvent>( dword pevHandle, dword messageHandle );
```

## Description

A callback function with this signature must be passed to the CAPL function [AREthAddEvent](CAPLfunctionAREthAddEvent.md). The callback is called before sending. The values of the SOME/IP message can be changed or updated before sending.

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
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);
  // create Service Instance
  psi = AREthCreateProvidedServiceInstance(aep,10,1);
  // create Eventgroup
  peg = AREthAddProvidedEventGroup(psi,1);
  // create Event and add Event to Eventgroup
  pev = AREthAddEvent(psi, 1, "OnPrepareEvent1 ");
  AREthAddEventToEventgroup(peg, pev);
  // ensure that Event is sent cyclically
  AREthSetProperty(pev,"CycleTimeMs",1000);
}

void OnPrepareEvent1 (DWORD eventHandle, DWORD messageHandle)
{
  // this function is called before the Event is sent. Parameters can be specified here.
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
