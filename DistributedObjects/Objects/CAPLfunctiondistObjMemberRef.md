[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Objects/CAPLfunctiondistObjMemberRef.md)

## CAPL Functions » Distributed Objects » distObjMemberRef

### Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax
- `distObjMemberRef *`
- `distObjMemberRef <Member>`

### Method Syntax
- [distObjMemberRef::IsConnected](../Methods/CAPLfunctiondistObjRefIsConnected.md)
- [distObjMemberRef::Subscribe](../Methods/CAPLfunctiondistObjMemberRefSubscribe.md)
- [distObjMemberRef::Unsubscribe](../Methods/CAPLfunctiondistObjMemberRefUnsubscribe.md)
- [distObjMemberRef::Announce](../Methods/CAPLfunctiondistObjMemberRefAnnounce.md)
- [distObjMemberRef::Unannounce](../Methods/CAPLfunctiondistObjMemberRefUnannounce.md)

### Description
References a distributed object member. This type cannot be used in declarations.

### Parameters
- **Member**: Path of a distributed object member.

### Selectors

- **Path**
  - Type: `char[]`
  - Access Limitation: Read only

- **Direction**
  - Type: `enum DOMemberDirection`
  - Access Limitation: Read only

- **VirtualNetwork**
  - Type: `virtNet`
  - Access Limitation: Read only
  - Note: Only available for consumed/provided members.

- **HasValidBinding**
  - Type: `dword`
  - Access Limitation: Read only
  - Note:
    - Only available for consumed/provided members.
    - Not valid for member at DO reference (`distObjReferenceRef <T>`).

- **SubscriptionState**
  - Type: `valueHandle uint32`
  - Access Limitation: Read only
  - Note:
    - Only available for consumed data/event/field member if the publish-subscribe pattern is used.
    - The referenced value is immutable.

- **AnnouncementState**
  - Type: `valueHandle uint32`
  - Access Limitation: Read only
  - Note:
    - Only available for provided data/event/field member if the publish-subscribe pattern with announcements is used.
    - The referenced value is immutable.

### Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  write("Member Path: %s", object.ExampleMember.Path);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
