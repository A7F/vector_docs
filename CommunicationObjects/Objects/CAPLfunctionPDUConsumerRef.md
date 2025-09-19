# pduConsumerRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `pduConsumerRef * <var>; // form 1`
- `pduConsumerRef <PDU> <var>; // form 2`
- `pduConsumerRef <Datatype> <var>; // form 3`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [pduConsumerRef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [pduConsumerRef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [pduConsumerRef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [pduConsumerRef::SetPDU](../Methods/CAPLfunctionSetPDU.md)
- [pduConsumerRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References a PDU consumer endpoint.

## Parameters

- **PDU**: PDU of a service, determining the data type of the object.
- **DataType**: Data type of the object (a PDU definition).

## Selectors

- **Name**: Name of the consumer endpoint  
  Type: `char[]`  
  Access Limitation: Read only

- **Path**: Full path of the consumer endpoint (including namespaces)  
  Type: `char[]`  
  Access Limitation: Read only

- **IsConsistent**: Returns whether the object refers to an existing endpoint.  
  Type: `dword`  
  Access Limitation: Read only

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible.  
  Type: `dword`  
  Access Limitation: Read only

- **ConsumerIndex**: Index of the consumer. Note that the index may change if consumers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **ServiceIndex**: Reference to the consumer of the service containing the PDU.  
  Type: `serviceConsumerRef *`  
  Access Limitation: Read only

## Example

```plaintext
pduConsumerRef MirrorAdjustment.StatusPDU pdu1;
pdu1 = MirrorAdjustment.consumerSide[CANoe].StatusPDU;
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [rxPDURef](CAPLfunctionRxPDURef.md) • [consumedPDURef](CAPLfunctionConsumedPDURef.md)
