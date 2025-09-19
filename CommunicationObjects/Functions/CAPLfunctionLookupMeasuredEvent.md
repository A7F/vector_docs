# LookupMeasuredEvent (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
measuredEventRef * LookupMeasuredEvent(char[] path);
```

## Description

Searches for the specified measured event. The path must be complete including namespaces and both endpoints: `(Namespace::)+Service.measure[consumer,provider].Event`.

You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the measured event.

## Return Values

The measured event. An uninitialized object if the event is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```c
measuredEventRef MirrorAdjustment.Position positionEvent;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char provider[20] = "LeftMirror";
char event[20] = "Position";

snprintf(path, elcount(path), "%s.measure[%s,%s].%s", service, consumer, provider, event);
positionEvent = (measuredEventRef MirrorAdjustment.Position) lookupMeasuredEvent(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupMeasuredField](CAPLfunctionLookupMeasuredField.md) • [LookupConsumedEvent](CAPLfunctionLookupConsumedEvent.md)
