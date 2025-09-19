# distObjEventRef

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`distObjEventRef <Member>`

## Method Syntax

[distObjEventRef::Trigger](../Methods/CAPLfunctiondistObjEventRefTrigger.md)

## Description

References a distributed object event member. This type cannot be used in declarations. This is a subtype of [distObjMemberRef `<Member>`](CAPLfunctiondistObjMemberRef.md) and `valueHandle <DataType>`. The referenced value is immutable for consumed members and mutable otherwise.

## Parameters

- **Member**: Path of a distributed object event member.

## Selectors

—

## Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  object.ExampleEventMember;
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
