# distObjRef

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `distObjRef *`
- `distObjRef <Interface>`
- `distObjRef reverse<<Interface>>`

## Method Syntax

- [distObjRef::Connect](../Methods/CAPLfunctiondistObjRefConnect.md)
- [distObjRef::ConnectTo](../Methods/CAPLfunctiondistObjRefConnectTo.md)
- [distObjRef::Disconnect](../Methods/CAPLfunctiondistObjRefDisconnect.md)
- [distObjRef::DisconnectFrom](../Methods/CAPLfunctiondistObjRefDisconnectFrom.md)
- [distObjRef::IsConnected](../Methods/CAPLfunctiondistObjRefIsConnected.md)
- [distObjRef::IsConnectedTo](../Methods/CAPLfunctiondistObjRefIsConnectedTo.md)
- [distObjRef::SubscribeAll](../Methods/CAPLfunctiondistObjRefSubscribeAll.md)
- [distObjRef::UnsubscribeAll](../Methods/CAPLfunctiondistObjRefUnsubscribeAll.md)
- [distObjRef::AnnounceAll](../Methods/CAPLfunctiondistObjRefAnnounceAll.md)
- [distObjRef::UnannounceAll](../Methods/CAPLfunctiondistObjRefUnannounceAll.md)

## Description

References a distributed object that is derived from the denoted interface.

## Parameters

- **Interface**: The optionally qualified name of a distributed object interface.
- **`reverse<Interface>`**: The reverse of a distributed object interface.

## Selectors

- **Name**: Name of the object.  
  Type: `char[]`  
  Access Limitation: Read only

- **Path**: Path of the object.  
  Type: `char[]`  
  Access Limitation: Read only

- **IsValid**: 1 if a valid object is referenced, 0 otherwise.  
  Type: `dword`  
  Access Limitation: Read only

- **AllMembersHaveValidBinding**: 1 if all members have a valid binding, 0 otherwise  
  Type: `dword`  
  Access Limitation: Read only

- **<Member Name>**: Access to a member of the object.  
  Type: `<MemberType>`  
  Access Limitation: Read only

- **<Embedded Member Name>**: Access to an embedded member of the object.  
  Type: `distObjRef <Embedded Member Interface>`  
  Access Limitation: Read only

- **<Reference Member Name>**: Access to a reference member of the object.  
  Type: `distObjReferenceRef <Reference Member Interface>`  
  Access Limitation: Read only

## Example

```plaintext
on start
{
  distObjRef reverse<::ExampleNamespace::ExampleInterface> x;
  distObjRef * y[42], z = ExampleNamespace::ExampleObject;
  x = (distObjRef reverse<ExampleInterface>)z;
  if (x.IsValid)
  {
    y[0] = x;
  }
  func(y[0]);
}

void func(distObjRef *& p)
{
  write("Path: %s", p.Path);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
