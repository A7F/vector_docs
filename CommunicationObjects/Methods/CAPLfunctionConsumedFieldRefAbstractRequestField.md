[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionConsumedFieldRefAbstractRequestField.md)

**CAPL Functions** » **Communication Objects** » **consumedFieldRef::AbstractRequestField**

# consumedFieldRef::AbstractRequestField (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

[int consumedFieldRef::AbstractRequestField()](../Objects/CAPLfunctionConsumedFieldRef.md)

## Description

Requests the subscription of a specific service field if abstract binding is used: for the specified consumer from the specified provider. If the field is requested, it will be subscribed as soon as the provider is connected with the consumer.

## Parameters

—

## Return Values

- **0**: Success
- **!= 0**: Failure

## Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition.AbstractRequestField();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedFieldRef::AbstractReleaseField](CAPLfunctionConsumedFieldRefAbstractReleaseField.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)