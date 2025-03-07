[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupProvidedPDU.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » LookupProvidedPDU

# LookupProvidedPDU (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
providedPDURef * LookupProvidedPDU(char[] path);
```

## Description

Searches for the specified provided PDU. The path must be complete including namespaces and both endpoints: `(Namespace::)+Service.providerSide[consumer,provider].PDU`. You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the provided PDU.

## Return Values

The provided PDU. An uninitialized object if the PDU is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```plaintext
providedPduRef MirrorAdjustment.Status statusPDU;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char provider[20] = "LeftMirror";
char pduName[20] = "Status";

snprintf(path, elcount(path), "%s.providerSide[%s,%s].%s", service, consumer, provider, pduName);
statusPDU = (providedPDURef MirrorAdjustment.Status) lookupProvidedPDU(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupProvidedEvent](CAPLfunctionLookupProvidedEvent.md) • [LookupConsumedPDU](CAPLfunctionLookupConsumedPDU.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)