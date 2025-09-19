# on Abstract_EventUnsubscribed (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
on Abstract_EventUnsubscribed <Event>;
```

## Description

The event procedure is called at the provider when an event is unsubscribed by a consumer and abstract binding is used.

## Parameters

- **`<event>`**: Designates the event on which the event procedure shall react. This must be a provider endpoint.

## Selectors

- **consumer**: Consumer, the type is [eventConsumerRef *](../Objects/CAPLfunctionEventConsumerRef.md)

## Example

```plaintext
on Abstract_EventUnsubscribed MirrorAdjustment[LeftMirror].CurrentPosition
{
  write("Event unsubscribed by %s", this.consumer.Name);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on Abstract_EventSubscribed](CAPLfunctionOnAbstractEventSubscribed.md)
