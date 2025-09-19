# LookupConsumedField (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
consumedFieldRef * LookupConsumedField(char[] path);
```

## Description

Searches for the specified consumed field. The path must be complete including namespaces and both endpoints: `(Namespace::)+Service.consumerSide[consumer,provider].Field`. You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the consumed field.

## Return Values

The consumed field. An uninitialized object if the field is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```plaintext
consumedFieldRef MirrorAdjustment.Position positionField;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char provider[20] = "LeftMirror";
char field[20] = "Position";

snprintf(path, elcount(path), "%s.consumerSide[%s,%s].%s", service, consumer, provider, field);
positionField = (consumedFieldRef MirrorAdjustment.Position) lookupConsumedField(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupConsumedEvent](CAPLfunctionLookupConsumedEvent.md) • [LookupProvidedField](CAPLfunctionLookupProvidedField.md)
