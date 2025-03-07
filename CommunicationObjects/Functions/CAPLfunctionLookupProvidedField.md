[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupProvidedField.md)

**CAPL Functions** » **Communication Objects** » **LookupProvidedField**

# LookupProvidedField (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
providedFieldRef * LookupProvidedField(char[] path);
```

## Description

Searches for the specified provided field. The path must be complete including namespaces and both endpoints: `(Namespace::)+Service.providerSide[consumer,provider].Field`.

You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the provided field.

## Return Values

The provided field. An uninitialized object if the field is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```plaintext
providedFieldRef MirrorAdjustment.Position positionField;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char provider[20] = "LeftMirror";
char field[20] = "Position";

snprintf(path, elcount(path), "%s.providerSide[%s,%s].%s", service, consumer, provider, field);
positionField = (providedFieldRef MirrorAdjustment.Position) lookupProvidedField(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupProvidedEvent](CAPLfunctionLookupProvidedEvent.md) • [LookupConsumedField](CAPLfunctionLookupConsumedField.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)