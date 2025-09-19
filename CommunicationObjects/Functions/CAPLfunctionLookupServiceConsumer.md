# LookupServiceConsumer (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
serviceConsumerRef * LookupServiceConsumer(char[] path);
```

## Description

Searches for the specified service consumer. The path must be complete including namespaces and endpoint: `(Namespace::)+Service[consumer]`.

You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the service consumer.

## Return Values

The service consumer. An uninitialized object if the service consumer is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```plaintext
serviceConsumerRef MirrorAdjustment mirrorSvc;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";

snprintf(path, elcount(path), "%s[%s]", service, consumer);
mirrorSvc = (serviceConsumerRef MirrorAdjustment) lookupServiceConsumer(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupEventConsumer](CAPLfunctionLookupEventConsumer.md) • [LookupServiceProvider](CAPLfunctionLookupServiceProvider.md)
