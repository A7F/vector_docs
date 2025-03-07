[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupEventProvider.md)

## CAPL Functions » Communication Objects » LookupEventProvider

# LookupEventProvider (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Function Syntax

```plaintext
eventProviderRef * LookupEventProvider(char[] path);
```

### Description

Searches for the specified event provider. The path must be complete including namespaces, endpoint and event: `(Namespace::)+Service[provider].Event`.

You can downcast the result to a concrete type, see the example.

### Parameters

- **path**: Path of the event provider.

### Return Values

The event provider. An uninitialized object if the event provider is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

### Example

```plaintext
eventProviderRef MirrorAdjustment.Position positionEvent;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char provider[20] = "LeftMirror";
char eventName[20] = "Position";

snprintf(path, elcount(path), "%s[%s].%s", service, provider, eventName);
positionEvent = (eventProviderRef MirrorAdjustment.Position) lookupEventProvider(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupFieldProvider](CAPLfunctionLookupFieldProvider.md) • [LookupEventConsumer](CAPLfunctionLookupEventConsumer.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)