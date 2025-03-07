[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Objects/CAPLfunctionEventConsumerRef.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » eventConsumerRef

# eventConsumerRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `eventConsumerRef * <var>;` // form 1
- `eventConsumerRef <Event> <var>;` // form 2
- `eventConsumerRef <Datatype> <var>;` // form 3

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [eventConsumerRef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [eventConsumerRef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [eventConsumerRef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [eventConsumerRef::SetEvent](../Methods/CAPLfunctionSetEvent.md)
- [eventConsumerRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References an event consumer endpoint.

## Parameters

- **Event**: Event of a service, determining the data type of the object.
- **DataType**: Data type of the object.

## Selectors

- **Name**: Name of the consumer endpoint.  
  Type: `char[]`  
  Access Limitation: Read only

- **Path**: Full path of the consumer endpoint (including namespaces).  
  Type: `char[]`  
  Access Limitation: Read only

- **IsConsistent**: Returns whether the object refers to an existing endpoint.  
  Type: `dword`  
  Access Limitation: Read only

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example).  
  Type: `dword`  
  Access Limitation: Read only

- **ConsumerIndex**: Index of the consumer. Note that the index may change if providers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **ServiceConsumer**: Reference to the consumer of the service containing the event.  
  Type: `serviceConsumerRef*`  
  Access Limitation: Read only

## Example

```plaintext
eventConsumerRef long event1;
event1 = MirrorAdjustment.consumerSide[LeftMirror].CurrentPosition;
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)