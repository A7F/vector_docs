# consumedMethodRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `consumedMethodRef * <var>;` // form 1
- `consumedMethodRef <Method> <var>;` // form 2
- `consumedMethodRef <Prototype> <var>;` // form 3

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [consumedMethodRef::CallAsync](../Methods/CAPLfunctionConsumedMethodRefCallAsync.md)
- [consumedMethodRef::CallAsyncPhys](../Methods/CAPLfunctionConsumedMethodRefCallAsyncPhys.md)
- [consumedMethodRef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [consumedMethodRef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [consumedMethodRef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [consumedMethodRef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [consumedMethodRef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [consumedMethodRef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [consumedMethodRef::SetMethod](../Methods/CAPLfunctionSetMethod.md)
- [consumedMethodRef::GetConsumedServiceRef](../Methods/CAPLfunctionGetConsumedServiceRef.md)
- [consumedMethodRef::GetConsumedFieldRef](../Methods/CAPLfunctionGetConsumedFieldRef.md)
- [consumedMethodRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References a consumed method endpoint, which means a specific combination of consumer and provider for a service function on consumer side.

## Parameters

- **Method**: Method, determining the data type of the object.
- **Prototype**: Data type of the object (a function prototype/signature).

## Selectors

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

- **LatestCall**: Information about the latest call started at this endpoint.  
  Type: `struct`  
  Access Limitation: Read only

- **LatestReturn**: Information about the latest return received at this endpoint.  
  Type: `struct`  
  Access Limitation: Read only

## Example

```plaintext
consumedMethodRef MirrorAdjustment.Adjust method;
method = MirrorAdjustment.consumerSide[CANoe,LeftMirror].Adjust;
method.CallAsync(-50, 0);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
