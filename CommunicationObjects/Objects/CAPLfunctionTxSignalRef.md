# txSignalRef (obsolete)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » txSignalRef

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `txSignalRef * <var>; // form 1`
- `txSignalRef <Signal> <var>; // form 2`
- `txSignalRef <Datatype> <var>; // form 3`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [txSignalRef::SetSender](../Methods/CAPLfunctionSetSender.md)
- [txSignalRef::SetReceiver](../Methods/CAPLfunctionSetReceiver.md)
- [txSignalRef::GetSender](../Methods/CAPLfunctionGetSender.md)
- [txSignalRef::GetSenderIndex](../Methods/CAPLfunctionGetSenderIndex.md)
- [txSignalRef::GetReceiver](../Methods/CAPLfunctionGetReceiver.md)
- [txSignalRef::GetReceiverIndex](../Methods/CAPLfunctionGetReceiverIndex.md)
- [txSignalRef::SetSignal](../Methods/CAPLfunctionSetSignal.md)
- [txSignalRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References a tx signal endpoint (from where the signal is sent).

## Parameters

- **Signal**: Signal (in the new communication concept).
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

## Example

```plaintext
txSignalRef long signal1;
signal1 = StatusSignal.senderSide[CANoe];
$signal = newValue;
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [rxSignalRef](CAPLfunctionRxSignalRef.md)
