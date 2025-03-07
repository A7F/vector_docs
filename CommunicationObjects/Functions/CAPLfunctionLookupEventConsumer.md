[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupEventConsumer.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » LookupEventConsumer

# LookupEventConsumer (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
eventConsumerRef * LookupEventConsumer(char[] path);
```

## Description

Searches for the specified event consumer. The path must be complete including namespaces, endpoint and event: `(Namespace::)+Service[consumer].Event`.

You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the field consumer.

## Return Values

The event consumer. An uninitialized object if the event consumer is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```c
eventConsumerRef MirrorAdjustment.Position positionEvent;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char eventName[20] = "Position";

snprintf(path, elcount(path), "%s[%s].%s", service, consumer, eventName);
positionEvent = (eventConsumerRef MirrorAdjustment.Position) lookupEventConsumer(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupFieldConsumer](CAPLfunctionLookupFieldConsumer.md) • [LookupEventProvider](CAPLfunctionLookupEventProvider.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)