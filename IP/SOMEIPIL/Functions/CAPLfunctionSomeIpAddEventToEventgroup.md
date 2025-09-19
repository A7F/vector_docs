[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpAddEventToEventgroup.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpAddEventToEventgroup**

# SomeIpAddEventToEventgroup

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
LONG SomeIpAddEventToEventgroup( dword pevgHandle, dword pevHandle );
```

## Description

This function assigns an Event which was created by [SomeIpAddEvent](CAPLfunctionSomeIpAddEvent.md) to an Event Group which was created by [SomeIpAddProvidedEventGroup](CAPLfunctionSomeIpAddProvidedEventGroup.md).

The Event can be removed from the Event Group with [SomeIpRemoveEventFromEventGroup](CAPLfunctionSomeIpRemoveEventFromEventgroup.md).

## Parameters

- **pevgHandle**: Handle of the Event Group that should be assigned to an Event, see [SomeIpAddProvidedEventGroup](CAPLfunctionSomeIpAddProvidedEventGroup.md)
- **pevHandle**: Handle of the Event that should be assigned to the Event Group, see [SomeIpAddEvent](CAPLfunctionSomeIpAddEvent.md)

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

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

```markdown
