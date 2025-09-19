[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Objects/CAPLfunctionProvidedEventRef.md)

## CAPL Functions » Communication Objects » providedEventRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Function Syntax

- `providedEventRef * <var>; // form 1`
- `providedEventRef <Event> <var>; // form 2`
- `providedEventRef <Datatype> <var>; // form 3`

### [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [providedEventRef::Trigger](../Methods/CAPLfunctionProvidedEventRefTrigger.md)
- [providedEventRef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [providedEventRef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [providedEventRef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [providedEventRef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [providedEventRef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [providedEventRef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [providedEventRef::SetEvent](../Methods/CAPLfunctionSetEvent.md)
- [providedEventRef::GetProvidedServiceRef](../Methods/CAPLfunctionGetProvidedServiceRef.md)
- [providedEventRef::Clear](../Methods/CAPLfunctionClear.md)

### Description

References a provided event endpoint, which means a specific combination of consumer and provider for a service event on provider side.

### Parameters

- **Event**: Event of a service, determining the data type of the object.
- **DataType**: Data type of the object.

### Selectors

- **Name**: Name of the provided endpoint  
  **Type**: `char[]`  
  **Access Limitation**: Read only

- **Path**: Full path of the provided endpoint (including namespaces)  
  **Type**: `char[]`  
  **Access Limitation**: Read only

- **IsConsistent**: Returns whether the object refers to an existing endpoint.  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example).  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **ConsumerIndex**: Index of the consumer. Note that the index may change if consumers are added or removed.  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **SubscriptionState**: State of the event subscription:
  - Unavailable: there’s no connection between consumer and provider, the event cannot be subscribed.
  - Available: the event can be subscribed, but currently is not subscribed.
  - Subscribed: the event is subscribed.  
  **Type**: `enum`  
  **Access Limitation**: Read only

### Example

```plaintext
providedEventRef long ev1;
ev1 = MirrorAdjustment.providerSide[CANoe,LeftMirror].CurrentPosition;
ev1.Trigger();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
