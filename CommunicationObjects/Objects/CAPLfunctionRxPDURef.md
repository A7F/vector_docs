[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Objects/CAPLfunctionRxPDURef.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » rxPDURef

# rxPDURef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `rxPDURef * <var>; // form 1`
- `rxPDURef <PDU> <var>; // form 2`
- `rxPDURef <Datatype> <var>; // form 3`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [rxPDURef::SetSender](../Methods/CAPLfunctionSetSender.md)
- [rxPDURef::SetReceiver](../Methods/CAPLfunctionSetReceiver.md)
- [rxPDURef::GetSender](../Methods/CAPLfunctionGetSender.md)
- [rxPDURef::GetSenderIndex](../Methods/CAPLfunctionGetSenderIndex.md)
- [rxPDURef::GetReceiver](../Methods/CAPLfunctionGetReceiver.md)
- [rxPDURef::GetReceiverIndex](../Methods/CAPLfunctionGetReceiverIndex.md)
- [rxPDURef::SetPDU](../Methods/CAPLfunctionSetPDU.md)
- [rxPDURef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References an rx PDU endpoint (where the PDU is received).

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

- **SenderIndex**: Index of the sender (only if the PDU is not a broadcast PDU). Note that the index may change if senders are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **ReceiverIndex**: Index of the receiver. Note that the index may change if receivers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **`<SignalName>`**: Accesses the specified signal on the PDU.  
  Type: `<Data type of the signal>`

## Example

```plaintext
rxPduRef StatusPdu pdu1;
pdu1 = StatusPdu.receiverSide[CANoe];
currentValue = $pdu1.StatusSignal;
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [txPDURef](CAPLfunctionTxPDURef.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)