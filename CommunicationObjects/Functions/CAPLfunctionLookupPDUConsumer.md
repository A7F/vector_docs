[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupPDUConsumer.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » LookupPDUConsumer

# LookupPDUConsumer (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
pduConsumerRef * LookupPDUConsumer(char[] path);
```

## Description

Searches for the specified PDU consumer. The path must be complete including namespaces, endpoint and PDU: `(Namespace::)+Service[consumer].PDU`.

You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the PDU consumer.

## Return Values

The PDU consumer. An uninitialized object if the PDU consumer is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```plaintext
pduConsumerRef MirrorAdjustment.Status statusPDU;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char pduName[20] = "Status";

snprintf(path, elcount(path), "%s[%s].%s", service, consumer, pduName);
statusPDU = (pduConsumerRef MirrorAdjustment.Status) lookupPDUConsumer(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupEventConsumer](CAPLfunctionLookupEventConsumer.md) • [LookupPDUProvider](CAPLfunctionLookupPDUProvider.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)