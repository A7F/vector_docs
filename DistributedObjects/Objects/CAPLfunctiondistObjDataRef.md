[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Objects/CAPLfunctiondistObjDataRef.md)

## CAPL Functions » Distributed Objects » distObjDataRef

### Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

```
distObjDataRef <Member>
```

### Method Syntax
—

### Description
References a distributed object data member. This type cannot be used in declarations. This is a subtype of [distObjMemberRef `<Member>`](CAPLfunctiondistObjMemberRef.md) and `valueHandle <DataType>`. The referenced value is immutable for consumed members and mutable otherwise.

### Parameters
- **Member**: Path of a distributed object data member.

### Selectors
—

### Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  object.ExampleDataMember;
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
