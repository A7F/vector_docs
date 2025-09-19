[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupConsumedMethod.md)

## LookupConsumedMethod (obsolete)

**CAPL Functions** » **Communication Objects** » **LookupConsumedMethod**

**Valid for:** CANoe DE

### Function Syntax

```plaintext
consumedMethodRef * LookupConsumedMethod(char[] path);
```

### Description

Searches for the specified consumed method. The path must be complete including namespaces and both endpoints: `(Namespace::)+Service.consumerSide[consumer,provider].Method`. You can downcast the result to a concrete type, see the example.

### Parameters

- **path**: Path of the consumed method.

### Return Values

The consumed method. An uninitialized object if the method is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

### Example

```plaintext
consumedMethodRef MirrorAdjustment.Adjust adjustMethod;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char provider[20] = "LeftMirror";
char method[20] = "Adjust";

snprintf(path, elcount(path), "%s.consumerSide[%s,%s].%s", service, consumer, provider, method);
adjustMethod = (consumedMethodRef MirrorAdjustment.Adjust) lookupConsumedMethod(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupConsumedEvent](CAPLfunctionLookupConsumedEvent.md) • [LookupProvidedMethod](CAPLfunctionLookupProvidedMethod.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
