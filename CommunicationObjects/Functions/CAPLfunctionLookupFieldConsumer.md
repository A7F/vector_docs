[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupFieldConsumer.md)

**CAPL Functions** » **Communication Objects** » **LookupFieldConsumer**

# LookupFieldConsumer (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
fieldConsumerRef * LookupFieldConsumer(char[] path);
```

## Description

Searches for the specified field consumer. The path must be complete including namespaces, endpoint and field: `(Namespace::)+Service[consumer].Field`.

You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the field consumer.

## Return Values

The field consumer. An uninitialized object if the field consumer is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```plaintext
fieldConsumerRef MirrorAdjustment.Position positionField;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char fieldName[20] = "Position";

snprintf(path, elcount(path), "%s[%s].%s", service, consumer, fieldName);
positionField = (fieldConsumerRef MirrorAdjustment.Position) lookupFieldConsumer(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupEventConsumer](CAPLfunctionLookupEventConsumer.md) • [LookupFieldProvider](CAPLfunctionLookupFieldProvider.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)