[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthCreateProvidedServiceInstance.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthCreateProvidedServiceInstance**

# AREthCreateProvidedServiceInstance

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword AREthCreateProvidedServiceInstance( dword aepHandle, dword serviceId, dword instanceId );
```

## Description

This function creates a Provided Service Instance and adds it to an Application Endpoint which was created by [AREthOpenLocalApplicationEndpoint](CAPLfunctionAREthOpenLocalApplicationEndpoint.md).

Objects can be assigned to the Service Instance as follows:

- Event Groups: [AREthAddProvidedEventGroup](CAPLfunctionAREthAddProvidedEventGroup.md)
- Events: [AREthAddEvent](CAPLfunctionAREthAddEvent.md)
- Fields: [AREthAddField](CAPLfunctionAREthAddField.md)
- Methods: [AREthAddMethod](CAPLfunctionAREthAddMethod.md)

The Service Instance can be deleted again with [AREthReleaseProvidedServiceInstance](CAPLfunctionAREthReleaseProvidedServiceInstance.md).

## Parameters

- **aepHandle**: Handle of the Application Endpoint (see [AREthOpenLocalApplicationEndpoint](CAPLfunctionAREthOpenLocalApplicationEndpoint.md))
- **serviceId**: Service identifier
- **instanceId**: Instance identifier

## Return Values

- **0**: An error occurred. The error can be evaluated using the [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function.
- **>0**: Handle of the generated Provided Service Instance

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

**See Also**: [AREthAddEvent](CAPLfunctionAREthAddEvent.md#aanchor12631), [AREthAddEventToEventgroup](CAPLfunctionAREthAddEventToEventgroup.md#aanchor24957), [AREthAddField](CAPLfunctionAREthAddField.md#aanchor27760), [AREthAddMethod](CAPLfunctionAREthAddMethod.md#aanchor7650), [AREthReleaseProvidedServiceInstance](CAPLfunctionAREthReleaseProvidedServiceInstance.md#aanchor18406)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)