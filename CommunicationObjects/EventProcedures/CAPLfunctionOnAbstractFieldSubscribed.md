# on Abstract_FieldSubscribed (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
on Abstract_FieldSubscribed <Field>;
```

### Description

The event procedure is called at the provider when a field is subscribed by a consumer and abstract binding is used.

### Parameters

- **`<field>`**: Designates the field on which the event procedure shall react. This must be a provider endpoint.

### Selectors

- **consumer**: Consumer, the type is [fieldConsumerRef *](../Objects/CAPLfunctionFieldConsumerRef.md)

### Example

```plaintext
on Abstract_FieldSubscribed MirrorAdjustment[LeftMirror].CurrentPosition
{
  write("Field subscribed by %s", this.consumer.Name);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on Abstract_FieldUnsubscribed](CAPLfunctionOnAbstractFieldUnsubscribed.md)
