# on SOMEIP_EventGroupUnsubscribed (obsolete)

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```
On SOMEIP_EventGroupUnsubscribed <EventGroup>;
```

## Description

The event procedure is called at the provider when an event group is unsubscribed by a consumer and SOME/IP binding is used.

## Parameters

- **`<EventGroup>`**: Designates the event group on which the event procedure shall react. This must be a provider endpoint.

## Selectors

- **consumer**: Consumer, the type is [serviceConsumerRef *](../Objects/CAPLfunctionServiceConsumerRef.md)

## Example

```plaintext
on SOMEIP_EventGroupUnsubscribed MirrorAdjustment[LeftMirror].AllEvents
{
  write("Event group unsubscribed by %s", this.consumer.Name);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on SOMEIP_EventGroupSubscribed](CAPLfunctionOnSOMEIPEventGroupSubscribed.md)
