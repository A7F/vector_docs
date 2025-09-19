# consumedPduRef::AbstractRequestPdu (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

[int consumedPDURef::AbstractRequestPDU();](../Objects/CAPLfunctionConsumedPDURef.md)

## Description

Requests the subscription of a specific service PDU if abstract binding is used: for the specified consumer from the specified provider. If the PDU is requested, it will be subscribed as soon as the provider is connected with the consumer.

## Parameters

—

## Return Values

- **0**: Success
- **!= 0**: Failure

## Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].StatusPDU.AbstractRequestPDU();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedPduRef::AbstractReleasePdu](CAPLfunctionConsumedPduRefAbstractReleasePdu.md)
