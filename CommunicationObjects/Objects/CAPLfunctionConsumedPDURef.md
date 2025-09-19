# consumedPDURef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Function Syntax

- `consumedPDURef * <var>; // form 1`
- `consumedPDURef <PDU> <var>; // form 2`
- `consumedPDURef <Datatype> <var>; // form 3`

### Method Syntax

- [consumedPduRef::AbstractIsPduRequested](../Methods/CAPLfunctionConsumedPduRefAbstractIsPduRequested.md)
- [consumedPduRef::AbstractReleasePdu](../Methods/CAPLfunctionConsumedPduRefAbstractReleasePdu.md)
- [consumedPduRef::AbstractRequestPdu](../Methods/CAPLfunctionConsumedPduRefAbstractRequestPdu.md)
- [consumedPduRef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [consumedPduRef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [consumedPduRef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [consumedPduRef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [consumedPduRef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [consumedPduRef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [consumedPduRef::SetPDU](../Methods/CAPLfunctionSetPDU.md)
- [consumedPduRef::GetConsumedServiceRef](../Methods/CAPLfunctionGetConsumedServiceRef.md)
- [consumedPduRef::Clear](../Methods/CAPLfunctionClear.md)

### Description

References a consumed PDU endpoint, which means a specific combination of consumer and provider for a service PDU on consumer side.

### Parameters

- **PDU**: PDU of a service, determining the data type of the object.
- **DataType**: Data type of the object (a PDU definition).

### Selectors

- **Name**: Name of the consumed endpoint.  
  Type: `char[]`  
  Access Limitation: Read only

- **Path**: Full path of the consumed endpoint (including namespaces).  
  Type: `char[]`  
  Access Limitation: Read only

- **IsConsistent**: Returns whether the object refers to an existing endpoint.  
  Type: `dword`  
  Access Limitation: Read only

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example).  
  Type: `dword`  
  Access Limitation: Read only

- **ConsumerIndex**: Index of the consumer. Note that the index may change if consumers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **SubscriptionState**: State of the PDU subscription:
  - Unavailable: there’s no connection between consumer and provider, the PDU cannot be subscribed.
  - Available: the PDU can be subscribed, but currently is not subscribed.
  - Subscribed: the PDU is subscribed.  
  Type: `enum`  
  Access Limitation: Read only

- **`<SignalName>`**: Accesses the specified signal on the PDU.  
  Type: `<Data type of the signal>`

### Example

```plaintext
consumedPDURef MirrorAdjustment.StatusPDU pdu1;
pdu1 = MirrorAdjustment.consumerSide[CANoe,LeftMirror].StatusPDU;
pdu1.AbstractRequestPDU();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
