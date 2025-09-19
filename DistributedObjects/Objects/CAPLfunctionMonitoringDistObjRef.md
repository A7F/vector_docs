# monitoringDistObjRef

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `monitoringDistObjRef *`
- `monitoringDistObjRef <Interface>`
- `monitoringDistObjRef reverse<<Interface>>`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [monitoringDistObjRef::Connect](../Methods/CAPLfunctiondistObjRefConnect.md)
- [monitoringDistObjRef::ConnectTo](../Methods/CAPLfunctiondistObjRefConnectTo.md)
- [monitoringDistObjRef::Disconnect](../Methods/CAPLfunctiondistObjRefDisconnect.md)
- [monitoringDistObjRef::DisconnectFrom](../Methods/CAPLfunctiondistObjRefDisconnectFrom.md)
- [monitoringDistObjRef::IsConnected](../Methods/CAPLfunctiondistObjRefIsConnected.md)
- [monitoringDistObjRef::IsConnectedTo](../Methods/CAPLfunctiondistObjRefIsConnectedTo.md)

## Description

References a monitoring distributed object that is derived from the denoted interface. The interface must support monitoring.

## Parameters

- **Interface**: The optionally qualified name of a distributed object interface.
- **reverse<Interface>**: The reverse of a distributed object interface.

## Selectors

- **Name**: Name of the object.
  - Type: `char[]`
  - Access Limitation: Read only

- **Path**: Path of the object.
  - Type: `char[]`
  - Access Limitation: Read only

- **IsValid**: 1 if a valid object is referenced, 0 otherwise.
  - Type: `dword`
  - Access Limitation: Read only

- **AllMembersHaveValidBinding**: 1 if all members have a valid binding, 0 otherwise.
  - Type: `dword`
  - Access Limitation: Read only

- **<Member Name>**: Access to a member of the object.
  - Type: `<MemberType>`
  - Access Limitation: Read only

- **<Embedded Member Name>**: Access to an embedded member of the object.
  - Type: `monitoringDistObjRef <Embedded Member Interface>`
  - Access Limitation: Read only

- **<Reference Member Name>**: Access to a reference member of the object.
  - Type: `monitoringDistObjReferenceRef <Reference Member Interface>`
  - Access Limitation: Read only

## Example

```plaintext
//vCDL
version 2.0;
namespace ExampleNamespace
{
  [MonitoringSupport]
  interface ExampleInterface {
    provided data int32 d;
  }
  [Monitoring, Binding="Abstract"]
  reverse<ExampleInterface> ExampleObject;
}

// CAPL
on start
{
  monitoringDistObjRef reverse<::ExampleNamespace::ExampleInterface> x;
  monitoringDistObjRef * y[42], z = ExampleNamespace::ExampleObject;
  x = (monitoringDistObjRef reverse<ExampleInterface>)z;
  if (x.IsValid)
  {
    y[0] = x;
  }
  func(y[0]);
}

void func(monitoringDistObjRef *& p)
{
  write("Path: %s", p.Path);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
