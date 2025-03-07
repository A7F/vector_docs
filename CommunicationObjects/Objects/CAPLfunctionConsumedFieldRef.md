[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Objects/CAPLfunctionConsumedFieldRef.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » consumedFieldRef

# consumedFieldRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `consumedFieldRef * <var>;` // form 1
- `consumedFieldRef <Field> <var>;` // form 2
- `consumedFieldRef <Datatype> <var>;` // form 3

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [consumedFieldRef::AbstractIsFieldRequested](../Methods/CAPLfunctionConsumedFieldRefAbstractIsFieldRequested.md)
- [consumedFieldRef::AbstractReleaseField](../Methods/CAPLfunctionConsumedFieldRefAbstractReleaseField.md)
- [consumedFieldRef::AbstractRequestField](../Methods/CAPLfunctionConsumedFieldRefAbstractRequestField.md)
- [consumedFieldRef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [consumedFieldRef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [consumedFieldRef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [consumedFieldRef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [consumedFieldRef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [consumedFieldRef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [consumedFieldRef::SetField](../Methods/CAPLfunctionSetField.md)
- [consumedFieldRef::GetConsumedServiceRef](../Methods/CAPLfunctionGetProvidedServiceRef.md)
- [consumedFieldRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References a consumed field endpoint, which means a specific combination of consumer and provider for a service field on consumer side.

## Parameters

- **Field**: Field of a service, determining the data type of the object.
- **DataType**: Data type of the object.

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

- **Get**: Returns a reference to the Getter method.  
  **Type**: `consumedMethodRef`  
  **Access Limitation**: Read only

- **Set**: Returns a reference to the Setter method.  
  **Type**: `consumedMethodRef`  
  **Access Limitation**: Read only

- **ConsumerIndex**: Index of the consumer. Note that the index may change if consumers are added or removed.  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **SubscriptionState**: State of the field subscription:
  - Unavailable: there’s no connection between consumer and provider, the field cannot be subscribed.
  - Available: the field can be subscribed, but currently is not subscribed.
  - Subscribed: the field is subscribed.  
  **Type**: `enum`  
  **Access Limitation**: Read only

## Example

```plaintext
consumedFieldRef long field1;
field1 = MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition;
field1.AbstractRequestField();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)