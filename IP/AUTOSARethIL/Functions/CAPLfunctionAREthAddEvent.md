[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthAddEvent.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthAddEvent**

# AREthAddEvent

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword AREthAddEvent( dword psiHandle, dword eventId, char onPrepareEventCallback[] );
```

## Description

This function adds an Event to a Provided Service Instance that was created by [AREthCreateProvidedServiceInstance](CAPLfunctionAREthCreateProvidedServiceInstance.md).

[AREthTriggerEvent](CAPLfunctionAREthTriggerEvent.md) is used to trigger sending of the Event. Then, the CAPL Callback function [`<OnAREthPrepareEvent>`](CAPLfunctionOnAREthPrepareEvent.md) is called, and the application has the opportunity to change or update the values of the SOME/IP Event.

An Event can be removed again using the [AREthRemoveEvent](CAPLfunctionAREthRemoveEvent.md) function.

## Parameters

- **psiHandle**: Handle of the Provided-Service Instance
- **eventId**: Identifier of the Event
- **onPrepareEventCallback**: Name of the CAPL function, see CAPL callback [`<OnAREthPrepareEvent>`](CAPLfunctionOnAREthPrepareEvent.md)

## Return Values

- **0**: An error occurred. The error can be evaluated using the [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function.
- **>0**: Handle of the created Event

## Example

```plaintext
void Initialize()
{
  dword aep; // Application Endpoint handle
  dword psi; // provided service handle
  dword peg; // provided Eventgroup handle
  dword pev; // provided Event handle

  // open Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
  psi = AREthCreateProvidedServiceInstance(aep,10,1);

  // create Eventgroup
  peg = AREthAddProvidedEventGroup(psi,1);

  // create Event and add Event to Eventgroup
  pev = AREthAddEvent(psi, 1, "OnPrepareEvent1");
  AREthAddEventToEventgroup(peg, pev);

  // ensure that Event is sent cyclically
  AREthSetProperty(pev,"CycleTimeMs",1000);
}

void OnPrepareEvent1(dword eventHandle, dword messageHandle)
{
  // this function is called before the Event is sent. Parameters can be specified here.
}
```

[See Also](javascript:void(0);)
