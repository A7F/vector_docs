[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Objects/CAPLfunctionMonitoringDistObjContainerRef.md)

## CAPL Functions » Distributed Objects » monitoringDistObjContainerRef

### monitoringDistObjContainerRef

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

- `monitoringDistObjContainerRef *`
- `monitoringDistObjContainerRef <Typedef name>`

### Method Syntax

- [distObjContainerRef `<Typedef name>`::Create](../Methods/CAPLfunctiondistObjContainerRefCreate.md)
- [distObjContainerRef `<Typedef name>`::Erase](../Methods/CAPLfunctiondistObjContainerRefErase.md)
- [distObjContainerRef `<Typedef name>`::PopBack](../Methods/CAPLfunctiondistObjContainerRefPopBack.md)
- [distObjContainerRef `<Typedef name>`::PushBack](../Methods/CAPLfunctiondistObjContainerRefPushBack.md)
- [distObjContainerRef `<Typedef name>`::Resize](../Methods/CAPLfunctiondistObjContainerRefResize.md)

### Description

References a container of monitoring distributed objects.

The types provide an overload for the subscript operator to access the elements which have a [distObjRef](CAPLfunctiondistObjRef.md) or `distObjContainerRef` type. The wildcard container type (`monitoringDistObjContainerRef *`) cannot be used with the subscript operator but it is possible to downcast it with a runtime check to a more specialized type.

The leaf elements of containers can be iterated over with a for loop (same syntax as C++ range-based for loop). The leaf elements are visited in the same order as in a depth-first search. Invalid elements (only possible in object containers) are skipped.

Containers are **not** covariant in their element type, as they are mutable.

### Parameters

- **Typedef name**: The fully qualified name of a monitoring distributed object container.

### Selectors

- **Name**: Name of the reference.
  - Type: `char[]`
  - Access Limitation: Read only

- **Path**: Path of the reference.
  - Type: `char[]`
  - Access Limitation: Read only

- **IsValid**: 1 if a valid reference is referenced, 0 otherwise.
  - Type: `dword`
  - Access Limitation: Read only

- **Length**: Number of elements.
  - Type: `dword`
  - Access Limitation: Read-write only for list, Read only for array

### Example

```plaintext
version 2.0;
// vCDL
namespace ExampleNamespace
{
  [MonitoringSupport]
  interface ExampleInterface {
    provided data int32 d;
  }

  [Monitoring, Binding="Abstract"]
  ExampleInterface ExampleObject;
  [Monitoring, Binding="Abstract"]
  list<ExampleInterface> ExampleContainer;
}

// CAPL
on start
{
  ExampleContainer.PushBack();
  ExampleContainer.PushBack();
  WritePath(ExampleContainer[1]);
}

void WritePath(monitoringDistObjRef ExampleNamespace::ExampleInterface obj) {
  Write("%s", obj.Path);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
