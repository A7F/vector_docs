# consumedServiceRef::ReleaseService (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

```plaintext
int consumedServiceRef::ReleaseService();
```

## Description

Releases the usage of a specific service: for the specified consumer from the specified provider. If the service is released, the (logical) connection to the provider will be cut and not be reestablished automatically. Without the connection, the service can’t be used by the consumer.

## Parameters

—

## Return Values

- **0**: Success
- **!= 0**: Failure

## Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].ReleaseService();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedServiceRef::RequestService](CAPLfunctionConsumedServiceRefRequestService.md)
