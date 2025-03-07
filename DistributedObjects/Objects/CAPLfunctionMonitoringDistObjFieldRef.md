[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Objects/CAPLfunctionMonitoringDistObjFieldRef.md)

**CAPL Functions** » **Distributed Objects** » **monitoringDistObjFieldRef**

# monitoringDistObjFieldRef

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`monitoringDistObjFieldRef <Member>`

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

—

## Description

References a monitoring distributed object field member. This type cannot be used in declarations. This is a subtype of `monitoringDistObjMemberRef <Member>` and `valueHandle <DataType>`. The referenced value is immutable.

## Parameters

- **Member**: Path of a monitoring distributed object field member.

## Selectors

- **Get**: Embedded getter method.
  - Signature is `<FieldType> Get()`
  - Type: `monitoringDistObjMethodRef <Member>.Get`
  - Access Limitation: Read only

- **Set**: Embedded setter method.
  - Signature is `<FieldType> Set(FieldType)`
  - Type: `monitoringDistObjMethodRef <Member>.Set`
  - Access Limitation: Read only

## Example

—

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)