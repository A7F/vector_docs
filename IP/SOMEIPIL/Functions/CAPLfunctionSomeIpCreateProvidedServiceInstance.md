[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpCreateProvidedServiceInstance.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpCreateProvidedServiceInstance**

# SomeIpCreateProvidedServiceInstance

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword SomeIpCreateProvidedServiceInstance( dword aepHandle, dword serviceId, dword instanceId ); // form 1
dword SomeIpCreateProvidedServiceInstance( dword aepHandle, dword serviceId, dword instanceId, dword majorVersion, dword minorVersion ); // form 2
```

## Description

This function creates a Provided Service Instance and adds it to an Application Endpoint which was created by [SomeIpReleaseProvidedServiceInstance](CAPLfunctionSomeIpReleaseProvidedServiceInstance.md).

Objects can be assigned to the Service Instance as follows:

- Event Groups: [SomeIpAddProvidedEventGroup](CAPLfunctionSomeIpAddProvidedEventGroup.md)
- Events: [SomeIpAddEvent](CAPLfunctionSomeIpAddEvent.md)
- Fields: [SomeIpAddField](CAPLfunctionSomeIpAddField.md)
- Methods: [SomeIpAddMethod](CAPLfunctionSomeIpAddMethod.md)

The Service Instance can be deleted again with [SomeIpReleaseProvidedServiceInstance](CAPLfunctionSomeIpReleaseProvidedServiceInstance.md).

## Parameters

- **aepHandle**: Handle of the Application Endpoint (see [SomeIpOpenLocalApplicationEndpoint](CAPLfunctionSomeIpOpenLocalApplicationEndpoint.md))
- **serviceId**: Service identifier
- **instanceId**: Instance identifier
- **majorVersion**: Service interface major version.
- **minorVersion**: Service interface minor version.

## Return Values

- **0**: An error occurred. The error can be evaluated using the [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function.
- **>0**: Handle of the generated Provided Service Instance

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
