# consumedEventRef::AbstractReleaseEvent (obsolete)

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Method Syntax

```plaintext
int consumedEventRef::AbstractReleaseEvent();
```

## Description

Releases the subscription of a specific service event if abstract binding is used: for the specified consumer from the specified provider. If the event is released, it will be unsubscribed and not automatically re-subscribed.

## Parameters

—

## Return Values

- **0**: Success
- **!= 0**: Failure

## Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition.AbstractReleaseEvent();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedEventRef::AbstractRequestEvent](CAPLfunctionConsumedEventRefAbstractRequestEvent.md)
