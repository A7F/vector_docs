[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Objects/CAPLfunctionConsumedServiceRef.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » consumedServiceRef

# consumedServiceRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `consumedServiceRef * <var>; // form 1`
- `consumedServiceRef <Service> <var>; // form 2`
- `consumedServiceRef <Interface> <var>; // form 3`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [consumedServiceRef::IsServiceRequested](../Methods/CAPLfunctionConsumedServiceRefIsServiceRequested.md)
- [consumedServiceRef::ReleaseService](../Methods/CAPLfunctionConsumedServiceRefReleaseService.md)
- [consumedServiceRef::RequestService](../Methods/CAPLfunctionConsumedServiceRefRequestService.md)
- [consumedServiceRef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [consumedServiceRef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [consumedServiceRef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [consumedServiceRef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [consumedServiceRef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [consumedServiceRef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [consumedServiceRef::SetService](../Methods/CAPLfunctionSetService.md)
- [consumedServiceRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References a consumed service endpoint, which means a specific combination of consumer and provider for a service on consumer side.

## Parameters

- **Service**: Service, determining the data type of the object.
- **Interface**: Data type of the object (a service interface).

## Selectors

- **Name**: Name of the consumed endpoint.  
  **Type**: `char[]`  
  **Access Limitation**: Read only

- **Path**: Full path of the consumed endpoint (including namespaces).  
  **Type**: `char[]`  
  **Access Limitation**: Read only

- **IsConsistent**: Returns whether the object refers to an existing endpoint.  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example).  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **<eventName>**:  
  **Type**: `consumedEventRef`  
  **Access Limitation**: Read only

- **<fieldName>**:  
  **Type**: `consumedFieldRef`  
  **Access Limitation**: Read only

- **<pduName>**:  
  **Type**: `consumedPDURef`  
  **Access Limitation**: Read only

- **<methodName>**:  
  **Type**: `consumedMethodRef`  
  **Access Limitation**: Read only

- **ConsumerIndex**: Index of the consumer. Note that the index may change if consumers are added or removed.  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **ConnectionState**: State of the connection between consumer and provider:
  - Unavailable: service provider is currently not available, cannot connect
  - Connectable: consumer and provider can connect, but are not connected
  - Available: consumer and provider are connected, the service is available.  
  **Type**: `enum`  
  **Access Limitation**: Read only

## Example

```plaintext
consumedServiceRef MirrorAdjustment service;
service = MirrorAdjustment.consumerSide[CANoe,LeftMirror];
service.RequestService();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)