# consumedServiceRef::RequestService (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

```plaintext
int consumedServiceRef::RequestService();
```

## Description

Requests the usage of a specific service: for the specified consumer from the specified provider. If the service is requested, a (logical) connection to the provider will be created as soon as the provider is available for the consumer.

## Parameters

—

## Return Values

- **0**: Success
- **!= 0**: Failure

## Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].RequestService();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedServiceRef::ReleaseService](CAPLfunctionConsumedServiceRefReleaseService.md)
