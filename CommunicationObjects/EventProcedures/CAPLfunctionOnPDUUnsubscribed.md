[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/EventProcedures/CAPLfunctionOnPDUUnsubscribed.md)

**CAPL Functions** » **Communication Objects** » **on PDU_Unsubscribed**

# on PDU_Unsubscribed (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
on PDU_Unsubscribed <PDU>;
```

## Description

The event procedure is called at the provider when a PDU is unsubscribed by a consumer.

## Parameters

- **<PDU>**: Designates the PDU on which the event procedure shall react. This must be a provider endpoint.

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)