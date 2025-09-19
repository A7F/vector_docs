[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthAddEventToEventgroup.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthAddEventToEventgroup**

# AREthAddEventToEventgroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
LONG AREthAddEventToEventgroup( dword pevgHandle, dword pevHandle );
```

## Description

This function assigns an Event which was created by [AREthAddEvent](CAPLfunctionAREthAddEvent.md) to an Event Group which was created by [AREthAddProvidedEventGroup](CAPLfunctionAREthAddProvidedEventGroup.md).

The Event can be removed from the Event Group with [AREthRemoveEventFromEventGroup](CAPLfunctionAREthRemoveEventFromEventgroup.md).

## Parameters

- **pevgHandle**: Handle of the Event Group that should be assigned to an Event, see [AREthAddProvidedEventGroup](CAPLfunctionAREthAddProvidedEventGroup.md)
- **pevHandle**: Handle of the Event that should be assigned to the Event Group, see [AREthAddEvent](CAPLfunctionAREthAddEvent.md)

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

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
