[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionConsumedEventRefAbstractIsEventRequested.md)

### CAPL Functions » Communication Objects » consumedEventRef::AbstractIsEventRequested

# consumedEventRef::AbstractIsEventRequested (obsolete)

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

**Method Syntax**

```plaintext
dword consumedEventRef::AbstractIsEventRequested();
```

**Description**

Returns whether the specified event is currently requested (if abstract binding is used).

**Parameters**

— 

**Return Values**

- **0**: Event is not currently requested
- **1**: Event is currently requested

**Example**

```plaintext
val = MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition.AbstractIsEventRequested();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedEventRef::AbstractReleaseEvent](CAPLfunctionConsumedEventRefAbstractReleaseEvent.md) • [consumedEventRef::AbstractRequestEvent](CAPLfunctionConsumedEventRefAbstractRequestEvent.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)