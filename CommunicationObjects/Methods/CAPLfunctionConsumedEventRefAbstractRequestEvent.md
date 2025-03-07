[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionConsumedEventRefAbstractRequestEvent.md)

## CAPL Functions » Communication Objects » consumedEventRef::AbstractRequestEvent

# consumedEventRef::AbstractRequestEvent (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Method Syntax

```plaintext
int consumedEventRef::AbstractRequestEvent();
```

### Description

Requests the subscription of a specific service event if abstract binding is used: for the specified consumer from the specified provider. If the event is requested, it will be subscribed as soon as the provider is connected with the consumer.

### Parameters

—

### Return Values

- **0**: Success
- **!= 0**: Failure

### Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition.AbstractRequestEvent();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedEventRef::AbstractReleaseEvent](CAPLfunctionConsumedEventRefAbstractReleaseEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)