[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionConsumedEventRefAbstractReleaseEvent.md)

**CAPL Functions** » **Communication Objects** » **consumedEventRef::AbstractReleaseEvent**

# consumedEventRef::AbstractReleaseEvent (obsolete)

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Method Syntax

```plaintext
int consumedEventRef::AbstractReleaseEvent();
```

## Description

Releases the subscription of a specific service event if abstract binding is used: for the specified consumer from the specified provider. If the event is released, it will be unsubscribed and not automatically re-subscribed.

## Parameters

—

## Return Values

- **0**: Success
- **!= 0**: Failure

## Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition.AbstractReleaseEvent();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedEventRef::AbstractRequestEvent](CAPLfunctionConsumedEventRefAbstractRequestEvent.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)