# LookupServiceProvider (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
serviceProviderRef * LookupServiceProvider(char[] path);
```

## Description

Searches for the specified service provider. The path must be complete including namespaces and endpoint: `(Namespace::)+Service [provider]`.

You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the service provider.

## Return Values

The service provider. An uninitialized object if the service provider is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```c
serviceProviderRef MirrorAdjustment mirrorSvc;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char provider[20] = "LeftMirror";

snprintf(path, elcount(path), "%s[%s]", service, provider);
mirrorSvc = (serviceProviderRef MirrorAdjustment) lookupServiceProvider(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupEventProvider](CAPLfunctionLookupEventProvider.md) • [LookupServiceConsumer](CAPLfunctionLookupServiceConsumer.md)
