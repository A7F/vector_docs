[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Objects/CAPLfunctionConsumedEventRef.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » consumedEventRef

# consumedEventRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `consumedEventRef * <var>; // form 1`
- `consumedEventRef <Event> <var>; // form 2`
- `consumedEventRef <Datatype> <var>; // form 3`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [consumedEventRef::AbstractIsEventRequested](../Methods/CAPLfunctionConsumedEventRefAbstractIsEventRequested.md)
- [consumedEventRef::AbstractReleaseEvent](../Methods/CAPLfunctionConsumedEventRefAbstractReleaseEvent.md)
- [consumedEventRef::AbstractRequestEvent](../Methods/CAPLfunctionConsumedEventRefAbstractRequestEvent.md)
- [consumedEventRef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [consumedEventRef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [consumedEventRef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [consumedEventRef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [consumedEventRef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [consumedEventRef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [consumedEventRef::SetEvent](../Methods/CAPLfunctionSetEvent.md)
- [consumedEventRef::GetConsumedServiceRef](../Methods/CAPLfunctionGetConsumedServiceRef.md)
- [consumedEventRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References a consumed event endpoint, which means a specific combination of consumer and provider for a service event on consumer side.

## Parameters

- **Event**: Event of a service, determining the data type of the object.
- **DataType**: Data type of the object.

## Selectors

- **Name**: Name of the consumed endpoint.  
  Type: `char[]`  
  Access Limitation: Read only

- **Path**: Full path of the consumed endpoint (including namespaces).  
  Type: `char[]`  
  Access Limitation: Read only

- **IsConsistent**: Returns whether the object refers to an existing endpoint.  
  Type: `char[]`  
  Access Limitation: Read only

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example).  
  Type: `char[]`  
  Access Limitation: Read only

- **ConsumerIndex**: Index of the consumer. Note that the index may change if consumers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **SubscriptionState**: State of the event subscription:
  - Unavailable: there’s no connection between consumer and provider, the event cannot be subscribed.
  - Available: the event can be subscribed, but currently is not subscribed.
  - Subscribed: the event is subscribed.  
  Type: `enum`  
  Access Limitation: Read only

## Example

```plaintext
consumedEventRef long ev1;
ev1 = MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition;
ev1.AbstractRequestEvent();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)