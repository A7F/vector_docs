[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionConsumedEventGroupRefSOMEIPRequestEventGroup.md)

**CAPL Functions** » **Communication Objects** » **consumedEventGroupRef::SOMEIPRequestEventGroup**

# consumedEventGroupRef::SOMEIPRequestEventGroup (obsolete)

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Method Syntax

```plaintext
int consumedEventGroupRef::SOMEIPRequestEventGroup();
```

## Description

Requests the subscription of a specific event group: for the specified consumer from the specified provider. If the event group is requested, it will be subscribed as soon as the provider is connected with the consumer.

## Parameters

—

## Return Values

- **0**: Success
- **!= 0**: Failure

## Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].AllEvents.SOMEIPRequestEventGroup();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedEventGroupRef::SOMEIPReleaseEventGroup](CAPLfunctionConsumedEventGroupRefSOMEIPReleaseEventGroup.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)