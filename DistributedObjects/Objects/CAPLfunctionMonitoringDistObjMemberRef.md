[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Objects/CAPLfunctionMonitoringDistObjMemberRef.md)

**CAPL Functions** » **Distributed Objects** » **monitoringDistObjMemberRef**

# monitoringDistObjMemberRef

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `monitoringDistObjMemberRef *`
- `monitoringDistObjMemberRef <Member>`

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `monitoringDistObjMemberRef::IsConnected`

## Description

References a monitoring distributed object member. This type cannot be used in declarations.

## Parameters

- **Member**: Path of a monitoring distributed object member.

## Selectors

- **Path**: char[], Read only
  - Path of the member.

- **Direction**: enum DOMemberDirection, Read only
  - Direction of the member.

- **VirtualNetwork**: virtNet, Read only
  - Virtual network the member is assigned to.
  - **Note**: Only available for consumed/provided members.

- **HasValidBinding**: dword, Read only
  - 1 if the member has a valid binding, 0 otherwise.
  - **Note**:
    - Only available for consumed/provided members.
    - Not valid for member at DO reference (`distObjReferenceRef <T>`).

- **SubscriptionState**: valueHandle uint32, Read only
  - Current subscription state of the member.
  - **Note**:
    - Only available for consumed data/event/field member if the publish-subscribe pattern is used.
    - The referenced value is immutable.

- **AnnouncementState**: Read only
  - Current announcement state of the member.
  - **Note**:
    - Only available for provided data/event/field member if the publish-subscribe pattern with announcements is used.
    - The referenced value is immutable.

## Example

```plaintext
on start
{
  monitoringDistObjRef ExampleInterface object = ExampleObject;
  write("Member Path: %s", object.ExampleMember.Path);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)