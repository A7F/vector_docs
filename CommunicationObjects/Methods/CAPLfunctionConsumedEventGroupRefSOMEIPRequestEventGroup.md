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
