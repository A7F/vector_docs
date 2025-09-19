# on PDU_Unsubscribed (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
on PDU_Unsubscribed <PDU>;
```

## Description

The event procedure is called at the provider when a PDU is unsubscribed by a consumer.

## Parameters

- **`<PDU>`**: Designates the PDU on which the event procedure shall react. This must be a provider endpoint.

## Selectors

- **consumer**: Consumer, the type is [pduConsumerRef *](../Objects/CAPLfunctionPDUConsumerRef.md)

## Example

```plaintext
on PDU_Unsubscribed Mirrors::MirrorAdjustment[LeftMirror].StatusPdu
{
  write("PDU unsubscribed by %s", this.consumer.Name);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on PDU_Subscribed](CAPLfunctionOnPDUSubscribed.md)
