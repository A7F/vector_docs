[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthRemoveFieldFromEventgroup.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » AREthRemoveFieldFromEventgroup

# AREthRemoveFieldFromEventgroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthRemoveFieldFromEventgroup( dword pevgHandle, dword pfHandle );
```

## Description

Removes a field created by [AREthAddField](CAPLfunctionAREthAddField.md) from an Event Group which was created by [AREthAddProvidedEventGroup](CAPLfunctionAREthAddProvidedEventGroup.md). The field itself is **not** deleted.

## Parameters

- **pevgHandle**: Handle of the Event Group from which a field should be removed (see [AREthAddProvidedEventGroup](CAPLfunctionAREthAddProvidedEventGroup.md)).
- **pfHandle**: Handle of the field that should be removed from the Event Group (see [AREthAddField](CAPLfunctionAREthAddField.md)).

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
  AREthAddEventToEventgroup(peg, pev);
  // ensure that Event is sent cyclically
  AREthSetProperty(pev,"CycleTimeMs",1000);
}

void OnPrepareEvent1(DWORD eventHandle, DWORD messageHandle)
{
  // this function is called before the Event is sent. Parameters can be specified here.
}

on key 'r'
{
  AREthRemoveFieldFromEventGroup (peg, pev);
}
```

[See Also](javascript:void(0);)