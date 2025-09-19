# consumedPduRef::AbstractIsPduRequested (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

dword [consumedPDURef](../Objects/CAPLfunctionConsumedPDURef.md)::AbstractIsPDURequested();

## Description

Returns whether the specified service PDU is currently requested (if abstract binding is used).

## Parameters

—

## Return Values

- **0**: PDU is not currently requested
- **1**: PDU is currently requested

## Example

```plaintext
val = MirrorAdjustment.consumerSide[CANoe,LeftMirror].StatusPDU.AbstractIsPDURequested();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedPduRef::AbstractReleasePdu](CAPLfunctionConsumedPduRefAbstractReleasePdu.md) • [consumedPduRef::AbstractRequestPdu](CAPLfunctionConsumedPduRefAbstractRequestPdu.md)
