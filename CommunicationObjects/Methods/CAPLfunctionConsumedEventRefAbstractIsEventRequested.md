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
