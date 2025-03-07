[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/EventProcedures/CAPLfunctionOnTransmitAnnounce.md)

**CAPL Functions** » [Distributed Objects](../CAPLfunctionsDOOverview.md) » on transmit_announce

# on transmit_announce

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`on transmit_announce <Member>;`

## Description

This handler is called whenever a provided data, event, or field member transmits an announce via the [CAPL binding](../../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).

If the member does not use the CAPL binding, the handler is ignored.

If there are multiple handlers for the same member, the measurement will be aborted.

## Parameters

- **<Member>**: Provided data, event or field member.

## Selectors

—

## Example

```plaintext
// example.vcdl
version 1.3;
namespace SomeNamespace {
  interface Example {
    [Binding="CAPL", HasAnnounceAPI=true]
    provided data int32 SomeData;
  }
  object Consumer : reverse<Example> {}
  object Provider : Example {}
}

// consumer_binding.can
variables {
  using namespace _SystemDataTypes::SDStates;
}
on transmit_subscribe Consumer.SomeData {
  Binding::SubscriptionStateReceived(Consumer.SomeData, DOMemberSubscription::Subscribed);
}

// provider.can
variables {
  using namespace _SystemDataTypes::SDStates;
}
on key 'a' {
  // toggle announcement
  if ($Provider.SomeData.AnnouncementState == DOMemberAnnouncement::Unannounced)
    Provider.SomeData.Announce();
  else
    Provider.SomeData.Unannounce();
}
on key 'b' {
  // increment value
  $Provider.SomeData++;
}

// provider_binding.can
variables {
  using namespace _SystemDataTypes::SDStates;
  enum DOMemberAnnouncement registry[char[]];
}
on transmit_announce Provider.SomeData {
  registry[Provider.SomeData.Path] = DOMemberAnnouncement::Announced;
  Binding::AnnouncementStateReceived(Provider.SomeData, DOMemberAnnouncement::Announced);
}
on transmit_unannounce Provider.SomeData {
  registry[Provider.SomeData.Path] = DOMemberAnnouncement::Unannounced;
  Binding::AnnouncementStateReceived(Provider.SomeData, DOMemberAnnouncement::Unannounced);
}
on transmit_value Provider.SomeData {
  if (registry[Provider.SomeData.Path] == DOMemberAnnouncement::Announced)
    Binding::ValueReceived(Consumer.SomeData, $this);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)