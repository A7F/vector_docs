[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Objects/CAPLfunctionRxSignalRef.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » rxSignalRef

# rxSignalRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `rxSignalRef * <var>;` // form 1
- `rxSignalRef <Signal> <var>;` // form 2
- `rxSignalRef <Datatype> <var>;` // form 3

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [rxSignalRef::SetSender](../Methods/CAPLfunctionSetSender.md)
- [rxSignalRef::SetReceiver](../Methods/CAPLfunctionSetReceiver.md)
- [rxSignalRef::GetSender](../Methods/CAPLfunctionGetSender.md)
- [rxSignalRef::GetSenderIndex](../Methods/CAPLfunctionGetSenderIndex.md)
- [rxSignalRef::GetReceiver](../Methods/CAPLfunctionGetReceiver.md)
- [rxSignalRef::GetReceiverIndex](../Methods/CAPLfunctionGetReceiverIndex.md)
- [rxSignalRef::SetSignal](../Methods/CAPLfunctionSetSignal.md)
- [rxSignalRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References an rx signal endpoint (where the signal is received).

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

- **SenderIndex**: Index of the sender (only if the PDU is not a broadcast PDU). Note that the index may change if senders are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **ReceiverIndex**: Index of the receiver. Note that the index may change if receivers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

## Example

```plaintext
rxSignalRef long signal1;
signal1 = StatusSignal.receiverSide[CANoe];
currentValue = $signal1;
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [txSignalRef](CAPLfunctionTxSignalRef.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)