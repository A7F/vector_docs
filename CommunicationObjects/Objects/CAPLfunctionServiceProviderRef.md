# serviceProviderRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `serviceProviderRef * <var>; // form 1`
- `serviceProviderRef <Service> <var>; // form 2`
- `serviceProviderRef <Interface> <var>; // form 3`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [serviceProviderRef::IsServiceProvided](../Methods/CAPLfunctionServiceProviderRefIsServiceProvided.md)
- [serviceProviderRef::ProvideService](../Methods/CAPLfunctionServiceProviderRefProvideService.md)
- [serviceProviderRef::ReleaseService](../Methods/CAPLfunctionServiceProviderRefReleaseService.md)
- [serviceProviderRef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [serviceProviderRef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [serviceProviderRef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [serviceProviderRef::SetService](../Methods/CAPLfunctionSetService.md)
- [serviceProviderRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References a service provider endpoint.

## Parameters

- **Service**: Service, determining the data type of the object.
- **Interface**: Data type of the object (a service interface).

## Selectors

- **Name**: Name of the provider endpoint  
  Type: `char[]`  
  Access Limitation: Read only

- **Path**: Full path of the provider endpoint (including namespaces)  
  Type: `char[]`  
  Access Limitation: Read only

- **IsConsistent**: Returns whether the object refers to an existing endpoint.  
  Type: `dword`  
  Access Limitation: Read only

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example).  
  Type: `dword`  
  Access Limitation: Read only

- `<eventName>`:  
  Type: `eventProviderRef`  
  Access Limitation: Read only

- `<fieldName>`:  
  Type: `fieldProviderRef`  
  Access Limitation: Read only

- `<pduName>`:  
  Type: `pduProviderRef`  
  Access Limitation: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **Address**: Generalized address of the endpoint. Can be used with binding-specific API like [Abstract_GetDisplayName](../Functions/CAPLfunctionAbstractGetDisplayName.md) to retrieve information.  
  Type: `AddressHandle`  
  Access Limitation: Read only

## Example

```plaintext
serviceProviderRef MirrorAdjustment svc1;
svc1 = MirrorAdjustment.providerSide[LeftMirror];
svc1.ProvideService();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [providedServiceRef](CAPLfunctionProvidedServiceRef.md)
