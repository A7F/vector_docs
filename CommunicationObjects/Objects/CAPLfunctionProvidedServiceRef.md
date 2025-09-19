# providedServiceRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `providedServiceRef * <var>;` // form 1
- `providedServiceRef <Service> <var>;` // form 2
- `providedServiceRef <Interface> <var>;` // form 3

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [providedServiceRef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [providedServiceRef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [providedServiceRef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [providedServiceRef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [providedServiceRef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [providedServiceRef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [providedServiceRef::SetService](../Methods/CAPLfunctionSetService.md)
- [providedServiceRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References a provided service endpoint, which means a specific combination of consumer and provider for a service on provider side.

## Parameters

- **Service**: Service, determining the data type of the object.
- **Interface**: Data type of the object (a service interface).

## Selectors

- **Name**: Name of the provided endpoint (Type: `char[]`, Access: Read only)
- **Path**: Full path of the provided endpoint (including namespaces) (Type: `char[]`, Access: Read only)
- **IsConsistent**: Returns whether the object refers to an existing endpoint. (Type: `dword`, Access: Read only)
- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example). (Type: `dword`, Access: Read only)
- **`<eventName>`**: (Type: `providedEventRef`, Access: Read only)
- **`<fieldName>`**: (Type: `providedFieldRef`, Access: Read only)
- **`<pduName>`**: (Type: `providedPDURef`, Access: Read only)
- **`<methodName>`**: (Type: `providedMethodRef`, Access: Read only)
- **ConsumerIndex**: Index of the consumer. Note that the index may change if consumers are added or removed. (Type: `dword`, Access: Read only)
- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed. (Type: `dword`, Access: Read only)
- **ConnectionState**: State of the connection between consumer and provider. (Type: `enum`, Access: Read only)
  - Unavailable: consumer and provider cannot currently connect.
  - Connectable: consumer and provider can connect, but are not connected.
  - Connected: consumer and provider are connected.

## Example

```plaintext
providedServiceRef MirrorAdjustment service1;
service1 = MirrorAdjustment.providerSide[CANoe,LeftMirror];
write("State: %d", $service1.ConnectionState);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
