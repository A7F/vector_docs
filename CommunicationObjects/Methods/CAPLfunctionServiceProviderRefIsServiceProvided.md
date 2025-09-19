# serviceProviderRef::IsServiceProvided (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

dword [serviceProviderRef](../Objects/CAPLfunctionServiceProviderRef.md)::IsServiceProvided();

## Description

Returns whether the service is currently provided at the endpoint.

## Parameters

—

## Return Values

- **0**: Service is not currently provided
- **1**: Service is currently provided

## Example

```plaintext
val = MirrorAdjustment.providerSide[LeftMirror].IsServiceProvided();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [serviceProviderRef::ProvideService](CAPLfunctionServiceProviderRefProvideService.md) • [serviceProviderRef::ReleaseService](CAPLfunctionServiceProviderRefReleaseService.md)
