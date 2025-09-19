# distObjFieldRef

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`distObjFieldRef <Member>`

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

## Description

References a distributed object field member. This type cannot be used in declarations. This is a subtype of [distObjMemberRef <Member>](CAPLfunctiondistObjMemberRef.md) and `valueHandle <DataType>`. The referenced value is immutable for consumed members and mutable otherwise.

## Parameters

- **Member**: Path of a distributed object field member.

## Selectors

- **Get**: Embedded getter method.  
  *Note*: Signature is `<FieldType> Get()`

  Type: `distObjMethodRef <Member>.Get`  
  Access Limitation: Read only

- **Set**: Embedded setter method.  
  *Note*: Signature is `<FieldType> Set(<FieldType>)`

  Type: `distObjMethodRef <Member>.Set`  
  Access Limitation: Read only

## Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  object.ExampleFieldMember.Get.CallAsync();
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
