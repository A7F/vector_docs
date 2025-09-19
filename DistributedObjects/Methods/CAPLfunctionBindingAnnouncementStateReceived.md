# Binding::AnnouncementStateReceived

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » Binding::AnnouncementStateReceived

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
long Binding::AnnouncementStateReceived(distObjDataRef * member, dword value);
long Binding::AnnouncementStateReceived(distObjEventRef * member, dword value);
long Binding::AnnouncementStateReceived(distObjFieldRef * member, dword value);
```

## Description

Sets the announcement state of a provided data, event, or field member value that uses the [CAPL binding](../../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md) and **PublishSubscribe** communication pattern with announcements.

## Parameters

- **member**: Member which receives a subscription state via the CAPL binding.
- **value**: Announcement state to be received.
  - Unannounced (0): `Announce()` was not yet called (after the last `Unannounce` call).
  - Announced (1): `Announce()` was called.

**Note**: One can use the enum `DOMemberAnnouncement` from the namespace `_SystemDataTypes::SDStates` (see example).

## Return Values

- **0**: OK
- **1**: No CAPL binding configured
- **2**: Wrong communication pattern
- **3**: No announcement at member
- **4**: Invalid announcement state value
- **5**: Wrong data type

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
