# serviceProviderRef::ReleaseService (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

```plaintext
int serviceProviderRef::ReleaseService();
```

## Description

Releases the service at the endpoint. This means that the binding will stop announcing the service or unregister it from a central registry (depending on the binding) and that connection requests from consumers will be denied.

## Parameters

—

## Return Values

- **0**: Success
- **!= 0**: Failure

## Example

```plaintext
MirrorAdjustment.providerSide[LeftMirror].ReleaseService();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [serviceProviderRef::ProvideService](CAPLfunctionServiceProviderRefProvideService.md)
