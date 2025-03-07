[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupProvidedService.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » LookupProvidedService

# LookupProvidedService (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
providedServiceRef * LookupProvidedService(char[] path);
```

## Description

Searches for the specified provided service. The path must be complete including namespaces and both endpoints: `(Namespace::)+Service.providerSide[consumer,provider]`.

You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the provided service.

## Return Values

The provided service. An uninitialized object if the service is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```plaintext
providedServiceRef MirrorAdjustment mirrorSvc;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char provider[20] = "LeftMirror";

snprintf(path, elcount(path), "%s.providerSide[%s,%s]", service, consumer, provider);
mirrorSvc = (providedServiceRef MirrorAdjustment) lookupProvidedService(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupProvidedEvent](CAPLfunctionLookupProvidedEvent.md) • [LookupConsumedService](CAPLfunctionLookupConsumedService.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)