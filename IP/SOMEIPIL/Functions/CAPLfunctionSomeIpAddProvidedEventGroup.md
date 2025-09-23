# SomeIpAddProvidedEventGroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword SomeIpAddProvidedEventGroup( dword psiHandle, dword eventGroupId );
```

## Description

This function adds an Event Group to a Provided Service Instance, which was created by [SomeIpCreateProvidedServiceInstance](CAPLfunctionSomeIpCreateProvidedServiceInstance.md).

Objects can be added to the Event Group as follows:

- Events: [SomeIpAddEventToEventGroup](CAPLfunctionSomeIpAddEventToEventgroup.md)
- Fields: [SomeIpAddFieldToEventGroup](CAPLfunctionSomeIpAddFieldToEventgroup.md)

An Event Group can be removed again using the [SomeIpRemoveProvidedEventGroup](CAPLfunctionSomeIpRemoveProvidedEventGroup.md) function.

## Parameters

- **psiHandle**: Handle of the Provided Service Instance that was created by [SomeIpCreateProvidedServiceInstance](CAPLfunctionSomeIpCreateProvidedServiceInstance.md).
- **eventGroupId**: Identifier of the Event Group

## Return Values

- **0**: An error occurred. The error can be evaluated using the [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function.
- **>0**: Handle of the created Provided Event Group

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

[See Also](javascript:void(0);)
