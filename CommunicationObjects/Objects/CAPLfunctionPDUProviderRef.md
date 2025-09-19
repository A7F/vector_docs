# pduProviderRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `pduProviderRef * <var>;` // form 1
- `pduProviderRef <PDU> <var>;` // form 2
- `pduProviderRef <Datatype> <var>;` // form 3

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [pduProviderRef::GetNrOfSubscribedConsumers](../Methods/CAPLfunctionPduProviderRefGetNrOfSubscribedConsumers.md)
- [pduProviderRef::GetSubscribedConsumer](../Methods/CAPLfunctionPduProviderRefGetSubscribedConsumer.md)
- [pduProviderRef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [pduProviderRef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [pduProviderRef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [pduProviderRef::SetPDU](../Methods/CAPLfunctionSetPDU.md)
- [pduProviderRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References a PDU provider endpoint.

## Parameters

- **PDU**: PDU of a service, determining the data type of the object.
- **DataType**: Data type of the object (a PDU definition).

## Selectors

- **Name**: Name of the provided endpoint  
  Type: `char[]`  
  Access Limitation: Read only

- **Path**: Full path of the provided endpoint (including namespaces)  
  Type: `char[]`  
  Access Limitation: Read only

- **IsConsistent**: Returns whether the object refers to an existing endpoint.  
  Type: `dword`  
  Access Limitation: Read only

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example).  
  Type: `dword`  
  Access Limitation: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **ServiceProvider**: Reference to the provider of the service containing the PDU.  
  Type: `serviceProviderRef *`  
  Access Limitation: Read only

- **`<SignalName>`**: Accesses the specified signal on the PDU.  
  Type: `<Data type of the signal>`

## Example

```plaintext
pduProviderRef MirrorAdjustment.StatusPDU pdu1;
pdu1 = MirrorAdjustment.providerSide[LeftMirror].StatusPDU;
$pdu1.StatusSignal = newValue;
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [txPDURef](CAPLfunctionTxPDURef.md) • [providedPDURef](CAPLfunctionProvidedPDURef.md)
