# serviceConsumerRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `serviceConsumerRef * <var>;` // form 1
- `serviceConsumerRef <Service> <var>;` // form 2
- `serviceConsumerRef <Interface> <var>;` // form 3

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [serviceConsumerRef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [serviceConsumerRef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [serviceConsumerRef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [serviceConsumerRef::SetService](../Methods/CAPLfunctionSetService.md)
- [serviceConsumerRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References a service consumer endpoint.

## Parameters

- **Service**: Service, determining the data type of the object.
- **Interface**: Data type of the object (a service interface).

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

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example).  
  Type: `dword`  
  Access Limitation: Read only

- `<eventName>`:  
  Type: `eventConsumerRef`  
  Access Limitation: Read only

- `<fieldName>`:  
  Type: `fieldConsumerRef`  
  Access Limitation: Read only

- `<pduName>`:  
  Type: `pduConsumerRef`  
  Access Limitation: Read only

- **ConsumerIndex**: Index of the consumer. Note that the index may change if consumers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **Address**: Generalized address of the endpoint. Can be used with binding-specific API like [Abstract_GetDisplayName](../Functions/CAPLfunctionAbstractGetDisplayName.md) to retrieve information.  
  Type: `AddressHandle`  
  Access Limitation: Read only

## Example

```plaintext
serviceConsumerRef MirrorAdjustment svc1;
svc1 = MirrorAdjustment.consumerSide[CANoe];
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedServiceRef](CAPLfunctionConsumedServiceRef.md)
