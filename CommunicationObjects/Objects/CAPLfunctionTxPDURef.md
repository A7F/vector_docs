# txPDURef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `txPDURef * <var>; // form 1`
- `txPDURef <PDU> <var>; // form 2`
- `txPDURef <Datatype> <var>; // form 3`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [txPDURef::SetSender](../Methods/CAPLfunctionSetSender.md)
- [txPDURef::SetReceiver](../Methods/CAPLfunctionSetReceiver.md)
- [txPDURef::GetSender](../Methods/CAPLfunctionGetSender.md)
- [txPDURef::GetSenderIndex](../Methods/CAPLfunctionGetSenderIndex.md)
- [txPDURef::GetReceiver](../Methods/CAPLfunctionGetReceiver.md)
- [txPDURef::GetReceiverIndex](../Methods/CAPLfunctionGetReceiverIndex.md)
- [txPDURef::SetPDU](../Methods/CAPLfunctionSetPDU.md)
- [txPDURef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References a tx PDU endpoint (from where the PDU is sent).

## Parameters

- **PDU**: PDU (in the new communication concept, but not in a service).
- **DataType**: Data type of the object.

## Selectors

- **Name**: Name of the endpoint  
  Type: `char[]`  
  Access Limitation: Read only

- **Path**: Full path of the endpoint (including namespaces)  
  Type: `char[]`  
  Access Limitation: Read only

- **IsConsistent**: Returns whether the object refers to an existing endpoint.  
  Type: `dword`  
  Access Limitation: Read only

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example).  
  Type: `dword`  
  Access Limitation: Read only

- **SenderIndex**: Index of the sender. Note that the index may change if senders are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **ReceiverIndex**: Index of the receiver (only if the PDU is not a broadcast PDU). Note that the index may change if receivers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **`<SignalName>`**: Accesses the specified signal on the PDU.  
  Type: `<Data type of the signal>`

## Example

```plaintext
txPduRef StatusPdu pdu1;
pdu1 = StatusPdu.senderSide[CANoe];
$pdu1.StatusSignal = newValue;
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [rxPDURef](CAPLfunctionRxPDURef.md)
