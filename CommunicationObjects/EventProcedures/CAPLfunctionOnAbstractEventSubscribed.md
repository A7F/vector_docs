# on Abstract_EventSubscribed (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
on Abstract_EventSubscribed <Event>;
```

## Description

The event procedure is called at the provider when an event is subscribed by a consumer and abstract binding is used.

## Parameters

- **`<event>`**: Designates the event on which the event procedure shall react. This must be a provider endpoint.

## Selectors

- **consumer**: Consumer, the type is [eventConsumerRef *](../Objects/CAPLfunctionEventConsumerRef.md)

## Example

```plaintext
on Abstract_EventSubscribed MirrorAdjustment[LeftMirror].CurrentPosition
{
  // send the event to the consumer on subscription
  providedEventRef long ev1;
  ev1 = MirrorAdjustment.providerSide[this.consumer.ConsumerIndex,LeftMirror].CurrentPosition;
  ev1.Trigger();
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on Abstract_EventUnsubscribed](CAPLfunctionOnAbstractEventUnsubscribed.md)
