[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionConsumedFieldRefAbstractIsFieldRequested.md)

## CAPL Functions » Communication Objects » consumedFieldRef::AbstractIsFieldRequested

# consumedFieldRef::AbstractIsFieldRequested (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Method Syntax

dword [consumedFieldRef](../Objects/CAPLfunctionConsumedFieldRef.md)::AbstractIsFieldRequested;

### Description

Returns whether the specified field is currently requested (if abstract binding is used).

### Parameters

—

### Return Values

- **0**: Field is not currently requested
- **1**: Field is currently requested

### Example

```plaintext
val = MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition.AbstractIsFieldRequested();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedFieldRef::AbstractReleaseField](CAPLfunctionConsumedFieldRefAbstractReleaseField.md) • [consumedFieldRef::AbstractRequestField](CAPLfunctionConsumedFieldRefAbstractRequestField.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)