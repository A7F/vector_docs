# consumedFieldRef::AbstractReleaseField (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

```plaintext
int consumedFieldRef::AbstractReleaseField();
```

## Description

Releases the subscription of a specific service field if abstract binding is used: for the specified consumer from the specified provider. If the field is released, it will be unsubscribed and not automatically re-subscribed.

## Parameters

—

## Return Values

- **0**: Success
- **!= 0**: Failure

## Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition.AbstractReleaseField();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedFieldRef::AbstractRequestField](CAPLfunctionConsumedFieldRefAbstractRequestField.md)
