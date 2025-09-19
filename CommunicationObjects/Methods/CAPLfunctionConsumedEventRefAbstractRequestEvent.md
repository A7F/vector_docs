# consumedEventRef::AbstractRequestEvent (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Method Syntax

```plaintext
int consumedEventRef::AbstractRequestEvent();
```

### Description

Requests the subscription of a specific service event if abstract binding is used: for the specified consumer from the specified provider. If the event is requested, it will be subscribed as soon as the provider is connected with the consumer.

### Parameters

—

### Return Values

- **0**: Success
- **!= 0**: Failure

### Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition.AbstractRequestEvent();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedEventRef::AbstractReleaseEvent](CAPLfunctionConsumedEventRefAbstractReleaseEvent.md)
