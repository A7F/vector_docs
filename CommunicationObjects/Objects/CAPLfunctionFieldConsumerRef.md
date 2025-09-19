# fieldConsumerRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `fieldConsumerRef * <var>;` // form 1
- `fieldConsumerRef <Field> <var>;` // form 2
- `fieldConsumerRef <Datatype> <var>;` // form 3

### Method Syntax

- [fieldConsumerRef::SetConsumer](../Methods/CAPLfunctionSetConsumer.md)
- [fieldConsumerRef::GetConsumer](../Methods/CAPLfunctionGetConsumer.md)
- [fieldConsumerRef::GetConsumerIndex](../Methods/CAPLfunctionGetConsumerIndex.md)
- [fieldConsumerRef::SetField](../Methods/CAPLfunctionSetField.md)
- [fieldConsumerRef::Clear](../Methods/CAPLfunctionClear.md)

### Description

References a field consumer endpoint.

### Parameters

- **Field**: Field of a service, determining the data type of the object.
- **DataType**: Data type of the object.

### Selectors

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

- **ServiceConsumer**: Reference to the consumer of the service containing the field.  
  Type: `serviceConsumerRef*`  
  Access Limitation: Read only

### Example

```plaintext
fieldConsumerRef long field1;
field1 = MirrorAdjustment.consumerSide[LeftMirror].CurrentPosition;
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
