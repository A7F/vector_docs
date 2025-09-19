# on Abstract_FieldUnsubscribed (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`on Abstract_FieldUnsubscribed <Field>;`

## Description

The event procedure is called at the provider when a field is unsubscribed by a consumer and abstract binding is used.

## Parameters

- **`<field>`**: Designates the field on which the event procedure shall react. This must be a provider endpoint.

## Selectors

- **consumer**: Consumer, the type is [fieldConsumerRef *](../Objects/CAPLfunctionFieldConsumerRef.md)

## Example

```plaintext
on Abstract_FieldUnsubscribed MirrorAdjustment[LeftMirror].CurrentPosition
{
  write("Field unsubscribed by %s", this.consumer.Name);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on Abstract_FieldSubscribed](CAPLfunctionOnAbstractFieldSubscribed.md)
