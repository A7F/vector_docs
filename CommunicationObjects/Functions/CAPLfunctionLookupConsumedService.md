# LookupConsumedService (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Function Syntax

```
consumedServiceRef * LookupConsumedService(char[] path);
```

### Description

Searches for the specified consumed service. The path must be complete including namespaces and both endpoints: `(Namespace::)+Service.consumerSide[consumer,provider]`.

You can downcast the result to a concrete type, see the example.

### Parameters

- **path**: Path of the consumed service.

### Return Values

The consumed service. An uninitialized object if the service is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

### Example

```c
consumedServiceRef MirrorAdjustment mirrorSvc;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char provider[20] = "LeftMirror";

snprintf(path, elcount(path), "%s.consumerSide[%s,%s]", service, consumer, provider);
mirrorSvc = (consumedServiceRef MirrorAdjustment) lookupConsumedService(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupConsumedEvent](CAPLfunctionLookupConsumedEvent.md) • [LookupProvidedService](CAPLfunctionLookupProvidedService.md)
