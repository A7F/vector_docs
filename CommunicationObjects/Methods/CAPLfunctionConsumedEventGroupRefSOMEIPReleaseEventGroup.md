# consumedEventGroupRef::SOMEIPReleaseEventGroup (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

[int consumedEventGroupRef::SOMEIPReleaseEventGroup();](../../../Shared/CAPL/General/ClassesAndObjects.md)

## Description

Releases the subscription of a specific event group: for the specified consumer from the specified provider. If the event group is released, it will be unsubscribed and not automatically re-subscribed.

## Parameters

—

## Return Values

- **0**: Success
- **!= 0**: Failure

## Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].AllEvents.SOMEIPReleaseEventGroup();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedEventGroupRef::SOMEIPRequestEventGroup](CAPLfunctionConsumedEventGroupRefSOMEIPRequestEventGroup.md)
