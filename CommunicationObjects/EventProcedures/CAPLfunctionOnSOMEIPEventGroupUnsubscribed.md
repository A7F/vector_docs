[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/EventProcedures/CAPLfunctionOnSOMEIPEventGroupUnsubscribed.md)

**CAPL Functions** » **Communication Objects** » **on SOMEIP_EventGroupUnsubscribed**

# on SOMEIP_EventGroupUnsubscribed (obsolete)

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```
On SOMEIP_EventGroupUnsubscribed <EventGroup>;
```

## Description

The event procedure is called at the provider when an event group is unsubscribed by a consumer and SOME/IP binding is used.

## Parameters

- **<EventGroup>**: Designates the event group on which the event procedure shall react. This must be a provider endpoint.

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)