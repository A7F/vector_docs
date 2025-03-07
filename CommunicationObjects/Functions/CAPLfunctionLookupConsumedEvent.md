[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupConsumedEvent.md)

## CAPL Functions » Communication Objects » LookupConsumedEvent (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Function Syntax

```plaintext
consumedEventRef * LookupConsumedEvent(char[] path);
```

### Description

Searches for the specified consumed event. The path must be complete including namespaces and both endpoints: `(Namespace::)+Service.consumerSide[consumer,provider].Event`.

You can downcast the result to a concrete type, see the example.

### Parameters

- **path**: Path of the consumed event.

### Return Values

The consumed event. An uninitialized object if the event is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

### Example

```plaintext
consumedEventRef MirrorAdjustment.Position positionEvent;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char provider[20] = "LeftMirror";
char event[20] = "Position";

snprintf(path, elcount(path), "%s.consumerSide[%s,%s].%s", service, consumer, provider, event);
positionEvent = (consumedEventRef MirrorAdjustment.Position) lookupConsumedEvent(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupConsumedField](CAPLfunctionLookupConsumedField.md) • [LookupProvidedEvent](CAPLfunctionLookupProvidedEvent.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)