# providedMethodRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `providedMethodRef * <var>; // form 1`
- `providedMethodRef <Method> <var>; // form 2`
- `providedMethodRef <Prototype> <var>; // form 3`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [providedMethodRef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [providedMethodRef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [providedMethodRef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [providedMethodRef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [providedMethodRef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [providedMethodRef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [providedMethodRef::SetMethod](../Methods/CAPLfunctionSetMethod.md)
- [providedMethodRef::GetProvidedServiceRef](../Methods/CAPLfunctionGetProvidedServiceRef.md)
- [providedMethodRef::GetProvidedFieldRef](../Methods/CAPLfunctionGetProvidedFieldRef.md)
- [providedMethodRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References a provided method endpoint, which means a specific combination of consumer and provider for a service function on provider side.

## Parameters

- **Method**: Method, determining the data type of the object.
- **Prototype**: Data type of the object (a function prototype / signature).

## Selectors

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

- **LatestCall**: Information about the latest call received at this endpoint.  
  **Type**: `struct`  
  **Access Limitation**: Read only

- **LatestReturn**: Information about the latest return sent from this endpoint.  
  **Type**: `struct`  
  **Access Limitation**: Read only

- **ParamDefaults**: Default values for automatic return of the function for the out parameters.  
  **Type**: `struct`  
  **Access Limitation**: Read only

- **DefaultResult**: Default value for automatic return of the function for the return value.  
  **Type**: `<Data Type of the function return value>`  
  **Access Limitation**: 

- **AutoAnswerMode**: Mode for automatic answering function calls:
  - Auto: calls are answered with the default values
  - OffOrManual: calls are not automatically answered
  - Discard: calls are discarded and will not be answered
  - AutoField: only for field getters and setters; use the field value to answer the call.  
  **Type**: `enum`  
  **Access Limitation**: 

- **AutoAnswerTimeNS**: Time in nonoseconds until the call is answered if the **AutoAnswerMode** is **Auto** or **AutoField**.  
  **Type**: `int64`  
  **Access Limitation**: 

## Example

```plaintext
providedMethodRef MirrorAdjustment.Adjust method1;
method1 = MirrorAdjustment.providerSide[CANoe,LeftMirror].Adjust;
$method1.AutoAnswerTimeNS = ADJUST_DEFAULT_ANSWER_TIME;
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
