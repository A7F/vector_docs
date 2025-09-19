[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Objects/CAPLfunctionProvidedPDURef.md)

## CAPL Functions » Communication Objects » providedPDURef

# providedPDURef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Function Syntax

- `providedPDURef * <var>; // form 1`
- `providedPDURef <PDU> <var>; // form 2`
- `providedPDURef <Datatype> <var>; // form 3`

### Method Syntax

- [providedPDURef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [providedPDURef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [providedPDURef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [providedPDURef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [providedPDURef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [providedPDURef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [providedPDURef::SetPDU](../Methods/CAPLfunctionSetPDU.md)
- [providedPDURef::GetProvidedServiceRef](../Methods/CAPLfunctionGetProvidedServiceRef.md)
- [providedPDURef::Clear](../Methods/CAPLfunctionClear.md)

### Description

References a provided PDU endpoint, which means a specific combination of consumer and provider for a service PDU on provider side.

### Parameters

- **PDU**: PDU of a service, determining the data type of the object.
- **DataType**: Data type of the object (a PDU definition).

### Selectors

- **Name**: Name of the provided endpoint  
  **Type**: char[]  
  **Access Limitation**: Read only

- **Path**: Full path of the provided endpoint (including namespaces)  
  **Type**: char[]  
  **Access Limitation**: Read only

- **IsConsistent**: Returns whether the object refers to an existing endpoint.  
  **Type**: dword  
  **Access Limitation**: Read only

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example).  
  **Type**: dword  
  **Access Limitation**: Read only

- **ConsumerIndex**: Index of the consumer. Note that the index may change if consumers are added or removed.  
  **Type**: dword  
  **Access Limitation**: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.  
  **Type**: dword  
  **Access Limitation**: Read only

- **SubscriptionState**: State of the PDU subscription:  
  - Unavailable: there’s no connection between consumer and provider, the PDU cannot be subscribed.
  - Available: the PDU can be subscribed, but currently is not subscribed.
  - Subscribed: the PDU is subscribed.  
  **Type**: enum  
  **Access Limitation**: Read only

- **`<SignalName>`**: Accesses the specified signal on the PDU.  
  **Type**: <Data type of the signal>  
  **Access Limitation**: 

### Example

```plaintext
providedPDURef MirrorAdjustment.StatusPDU pdu1;
pdu1 = MirrorAdjustment.providerSide[CANoe,LeftMirror].StatusPDU;
$pdu1.StatusSignal = newValue;
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)