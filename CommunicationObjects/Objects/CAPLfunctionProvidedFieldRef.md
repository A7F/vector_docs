# providedFieldRef (obsolete)

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

- `providedFieldRef * <var>; // form 1`
- `providedFieldRef <Field> <var>; // form 2`
- `providedFieldRef <Datatype> <var>; // form 3`

## [Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

- [providedFieldRef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [providedFieldRef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [providedFieldRef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [providedFieldRef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [providedFieldRef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [providedFieldRef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [providedFieldRef::SetField](../Methods/CAPLfunctionSetField.md)
- [providedFieldRef::GetProvidedServiceRef](../Methods/CAPLfunctionGetProvidedServiceRef.md)
- [providedFieldRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References a provided field endpoint, which means a specific combination of consumer and provider for a service field on provider side.

## Parameters

- **Field**: A field of a service, determining the data type of the object
- **DataType**: The data type of the object

## Selectors

- **Name**: Name of the provided endpoint  
  Type: `char[]`  
  Access Limitation: Read only

- **Path**: Full path of the provided endpoint (including namespaces)  
  Type: `char[]`  
  Access Limitation: Read only

- **IsConsistent**: Returns whether the object refers to an existing endpoint.  
  Type: `dword`  
  Access Limitation: Read only

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example).  
  Type: `dword`  
  Access Limitation: Read only

- **Get**: Returns a reference to the Getter method.  
  Type: `providedMethodRef`  
  Access Limitation: Read only

- **Set**: Returns a reference to the Setter method.  
  Type: `providedMethodRef`  
  Access Limitation: Read only

- **ConsumerIndex**: Index of the consumer. Note that the index may change if consumers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **SubscriptionState**: State of the field subscription:
  - Unavailable: there’s no connection between consumer and provider, the field cannot be subscribed.
  - Available: the field can be subscribed, but currently is not subscribed.
  - Subscribed: the field is subscribed.  
  Type: `enum`  
  Access Limitation: Read only

## Example

```plaintext
providedFieldRef long field1;
field1 = MirrorAdjustment.providerSide[CANoe,LeftMirror].CurrentPosition;
$field1 = newValue;
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

---
