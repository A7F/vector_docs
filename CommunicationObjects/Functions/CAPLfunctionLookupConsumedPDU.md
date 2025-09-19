# LookupConsumedPDU (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
consumedPDURef * LookupConsumedPDU(char[] path);
```

## Description

Searches for the specified consumed PDU. The path must be complete including namespaces and both endpoints: `(Namespace::)+Service.consumerSide[consumer,provider].PDU`.

You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the consumed PDU.

## Return Values

The consumed PDU. An uninitialized object if the PDU is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```c
consumedPduRef MirrorAdjustment.Status statusPDU;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char provider[20] = "LeftMirror";
char pduName[20] = "Status";

snprintf(path, elcount(path), "%s.consumerSide[%s,%s].%s", service, consumer, provider, pduName);
statusPDU = (consumedPDURef MirrorAdjustment.Status) lookupConsumedPDU(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupConsumedEvent](CAPLfunctionLookupConsumedEvent.md) • [LookupProvidedPDU](CAPLfunctionLookupProvidedPDU.md)
