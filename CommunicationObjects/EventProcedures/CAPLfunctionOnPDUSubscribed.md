# on PDU_Subscribed (obsolete)

**Valid for**: CANoe DE

## Function Syntax

```
on PDU_Subscribed <PDU>;
```

## Description

The event procedure is called at the provider when a PDU is subscribed by a consumer.

## Parameters

- **`<PDU>`**: Designates the PDU on which the event procedure shall react. This must be a provider endpoint.

## Selectors

- **consumer**: Consumer, the type is [pduConsumerRef *](../Objects/CAPLfunctionPDUConsumerRef.md)

## Example

```plaintext
on PDU_Subscribed Mirrors::MirrorAdjustment[LeftMirror].StatusPdu
{
  write("PDU subscribed by %s", this.consumer.Name);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on PDU_Unsubscribed](CAPLfunctionOnPDUUnsubscribed.md)
