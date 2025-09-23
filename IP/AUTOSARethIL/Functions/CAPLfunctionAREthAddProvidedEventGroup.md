# AREthAddProvidedEventGroup

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword AREthAddProvidedEventGroup( dword psiHandle, dword eventGroupId );
```

## Description

This function adds an Event Group to a Provided Service Instance, which was created by [AREthCreateProvidedServiceInstance](CAPLfunctionAREthCreateProvidedServiceInstance.md).

Objects can be added to the Event Group as follows:

- Events: [AREthAddEventToEventGroup](CAPLfunctionAREthAddEventToEventgroup.md)
- Fields: [AREthAddFieldToEventGroup](CAPLfunctionAREthAddFieldToEventgroup.md)

An Event Group can be removed again using the [AREthRemoveProvidedEventGroup](CAPLfunctionAREthRemoveProvidedEventGroup.md) function.

## Parameters

- **psiHandle**: Handle of the Provided Service Instance that was created by [AREthCreateProvidedServiceInstance](CAPLfunctionAREthCreateProvidedServiceInstance.md).
- **eventGroupId**: Identifier of the Event Group

## Return Values

- **0**: An error occurred. The error can be evaluated using the [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function.
- **>0**: Handle of the created Provided Event Group

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
