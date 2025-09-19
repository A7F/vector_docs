# LookupMeasuredService (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
measuredServiceRef * LookupMeasuredService(char[] path);
```

## Description

Searches for the specified measured service. The path must be complete including namespaces and both endpoints: `(Namespace::)+Service.measure[consumer,provider]`.

You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the measured service.

## Return Values

The measured service. An uninitialized object if the service is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```c
measuredServiceRef MirrorAdjustment mirrorSvc;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char provider[20] = "LeftMirror";

snprintf(path, elcount(path), "%s.measure[%s,%s]", service, consumer, provider);
mirrorSvc = (measuredServiceRef MirrorAdjustment) lookupMeasuredService(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupMeasuredEvent](CAPLfunctionLookupMeasuredEvent.md) • [LookupConsumedService](CAPLfunctionLookupConsumedService.md)
