[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpAddEvent.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpAddEvent

# SomeIpAddEvent

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword SomeIpAddEvent( dword psiHandle, dword eventId, char onPrepareEventCallback[] );
```

## Description

This function adds an Event to a Provided Service Instance that was created by [SomeIpCreateProvidedServiceInstance](CAPLfunctionSomeIpCreateProvidedServiceInstance.md).

[SomeIpTriggerEvent](CAPLfunctionSomeIpTriggerEvent.md) is used to trigger sending of the Event. Then, the CAPL Callback function [`<OnSomeIpPrepareEvent>`](CAPLfunctionOnSomeIpPrepareEvent.md) is called, and the application has the opportunity to change or update the values of the SOME/IP Event.

An Event can be removed again using the [SomeIpRemoveEvent](CAPLfunctionSomeIpRemoveEvent.md) function.

## Parameters

- **psiHandle**: Handle of the Provided-Service Instance
- **eventId**: Identifier of the Event
- **onPrepareEventCallback**: Name of the CAPL function, see CAPL callback [`<OnSomeIpPrepareEvent>`](CAPLfunctionOnSomeIpPrepareEvent.md)

## Return Values

- **0**: An error occurred. The error can be evaluated using the [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function.
- **>0**: Handle of the created Event

## Example

```plaintext
void Initialize()
{
  DWORD aep; // Application Endpoint handle
  DWORD psi; // provided service handle
  DWORD peg; // provided Eventgroup handle
  DWORD pev; // provided Event handle

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
```

See Also: [SomeIpAddEvent](#aanchor26478), [SomeIpAddEventToEventgroup](CAPLfunctionSomeIpAddEventToEventgroup.md#aanchor28752), [SomeIpAddField](CAPLfunctionSomeIpAddField.md#aanchor19206), [SomeIpAddFieldToEventgroup](CAPLfunctionSomeIpAddFieldToEventgroup.md#aanchor13758), [SomeIpAddMethod](CAPLfunctionSomeIpAddMethod.md#aanchor18130), [SomeIpAddProvidedEventGroup](CAPLfunctionSomeIpAddProvidedEventGroup.md#aanchor7027), [SomeIpCommitField](CAPLfunctionSomeIpCommitField.md#aanchor28811), [SomeIpCreateProvidedServiceInstance](CAPLfunctionSomeIpCreateProvidedServiceInstance.md#aanchor22704), [SomeIpReleaseProvidedServiceInstance](CAPLfunctionSomeIpReleaseProvidedServiceInstance.md#aanchor14904), [SomeIpRemoveEvent](CAPLfunctionSomeIpRemoveEvent.md#aanchor29702), [SomeIpRemoveEventFromEventgroup](CAPLfunctionSomeIpRemoveEventFromEventgroup.md#aanchor28297), [SomeIpRemoveField](CAPLfunctionSomeIpRemoveField.md#aanchor14135), [SomeIpRemoveFieldFromEventgroup](CAPLfunctionSomeIpRemoveFieldFromEventgroup.md#aanchor21774), [SomeIpRemoveMethod](CAPLfunctionSomeIpRemoveMethod.md#aanchor5943), [SomeIpRemoveProvidedEventGroup](CAPLfunctionSomeIpRemoveProvidedEventGroup.md#aanchor3761), [SomeIpTriggerEvent](CAPLfunctionSomeIpTriggerEvent.md#aanchor8579)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
