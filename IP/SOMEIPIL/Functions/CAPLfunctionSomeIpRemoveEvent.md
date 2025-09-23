# SomeIpRemoveEvent

[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpRemoveEvent.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpRemoveEvent**

## Function Syntax

```plaintext
long SomeIpRemoveEvent( dword pevHandle );
```

## Description

Removes an Event from a Provided Service Instance. The Event was previously added by [SomeIpAddEvent](CAPLfunctionSomeIpAddEvent.md).

Afterwards, the callback registered with [SomeIpAddEvent](CAPLfunctionSomeIpAddEvent.md) is no longer called. The Event is no longer sent by the SOME/IP IL.

## Parameters

- **pevHandle**: Handle of the Event that is to be removed. The handle must have been created with [SomeIpAddEvent](CAPLfunctionSomeIpAddEvent.md).

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

  // remove the Event
  SomeIpRemoveEvent(pev);

  // ... Event is removed from both Eventgroups and is not sent anymore
  // ... Application Endpoint, provided Service Instance and Eventgroup can still be used here
}
```

[See Also](javascript:void(0);)

- [SomeIpAddEvent](CAPLfunctionSomeIpAddEvent.md#aanchor26478)
- [SomeIpAddEventToEventgroup](CAPLfunctionSomeIpAddEventToEventgroup.md#aanchor28752)
- [SomeIpAddField](CAPLfunctionSomeIpAddField.md#aanchor19206)
- [SomeIpAddFieldToEventgroup](CAPLfunctionSomeIpAddFieldToEventgroup.md#aanchor13758)
- [SomeIpAddMethod](CAPLfunctionSomeIpAddMethod.md#aanchor18130)
- [SomeIpAddProvidedEventGroup](CAPLfunctionSomeIpAddProvidedEventGroup.md#aanchor7027)
- [SomeIpCommitField](CAPLfunctionSomeIpCommitField.md#aanchor28811)
- [SomeIpCreateProvidedServiceInstance](CAPLfunctionSomeIpCreateProvidedServiceInstance.md#aanchor22704)
- [SomeIpReleaseProvidedServiceInstance](CAPLfunctionSomeIpReleaseProvidedServiceInstance.md#aanchor14904)
- [SomeIpRemoveEvent](#aanchor29702)
- [SomeIpRemoveEventFromEventgroup](CAPLfunctionSomeIpRemoveEventFromEventgroup.md#aanchor28297)
- [SomeIpRemoveField](CAPLfunctionSomeIpRemoveField.md#aanchor14135)
- [SomeIpRemoveFieldFromEventgroup](CAPLfunctionSomeIpRemoveFieldFromEventgroup.md#aanchor21774)
- [SomeIpRemoveMethod](CAPLfunctionSomeIpRemoveMethod.md#aanchor5943)
- [SomeIpRemoveProvidedEventGroup](CAPLfunctionSomeIpRemoveProvidedEventGroup.md#aanchor3761)
- [SomeIpTriggerEvent](CAPLfunctionSomeIpTriggerEvent.md#aanchor8579)
