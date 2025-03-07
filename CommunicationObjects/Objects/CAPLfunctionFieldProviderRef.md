[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Objects/CAPLfunctionFieldProviderRef.md)

## CAPL Functions » Communication Objects » fieldProviderRef

# fieldProviderRef (obsolete)

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

### Function Syntax

- `fieldProviderRef * <var>; // form 1`
- `fieldProviderRef <Field> <var>; // form 2`
- `fieldProviderRef <Datatype> <var>; // form 3`

### [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [fieldProviderRef::GetNrOfSubscribedConsumers](../Methods/CAPLfunctionfieldProviderRefGetNrOfSubscribedConsumers.md)
- [fieldProviderRef::GetSubscribedConsumer](../Methods/CAPLfunctionfieldProviderRefGetSubscribedConsumer.md)
- [fieldProviderRef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [fieldProviderRef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [fieldProviderRef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [fieldProviderRef::SetField](../Methods/CAPLfunctionSetField.md)
- [fieldProviderRef::Clear](../Methods/CAPLfunctionClear.md)

### Description

References a field provider endpoint.

### Parameters

- **Field**: Field of a service, determining the data type of the object.
- **DataType**: Data type of the object.

### Selectors

- **Name**: Name of the provider endpoint  
  Type: `char[]`  
  Access Limitation: Read only

- **Path**: Full path of the provider endpoint (including namespaces)  
  Type: `char[]`  
  Access Limitation: Read only

- **IsConsistent**: Returns whether the object refers to an existing endpoint.  
  Type: `dword`  
  Access Limitation: Read only

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example).  
  Type: `dword`  
  Access Limitation: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **ServiceProvider**: Reference to the provider of the service containing the event.  
  Type: `serviceProviderRef*`  
  Access Limitation: Read only

### Example

```plaintext
fieldProviderRef long field1;
field1 = MirrorAdjustment.providerSide[LeftMirror].CurrentPosition;
$field1 = newValue;
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)