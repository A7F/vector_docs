# distObjInterfaceMember

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `distObjInterfaceMember *`
- `distObjInterfaceMember <Interface Member>`

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

## Description

The types of distributed object interface members. They are only useful for specifying value sets at type handlers (i.e. [any_value_update](../EventProcedures/CAPLfunctionOnAnyValueUpdate.md), …) and for accessing attributes at distributed object interface members.

All **distObjInterfaceMember** types are singleton types.

The types are not available for user declarations.

## Parameters

- **`<Interface Member>`**: The path of the interface member.

## Selectors

- **SubscriptionState**: Only available for consumed data/event/field member if the publish-subscribe pattern is used.  
  Type: `valueHandleSet uint32`  
  Access Limitation: Read only

- **AnnouncementState**: Only available for provided data/event/field member if the publish-subscribe pattern with announcements is used.  
  Type: `valueHandleSet uint32`  
  Access Limitation: Read only

- **LatestCall**: Only available for method member.  
  Type: `valueHandleSet <struct depending on signature>`  
  Access Limitation: Read only

- **LatestReturn**: Only available for method member.  
  Type: `valueHandleSet <struct depending on signature>`  
  Access Limitation: Read only

- **ParamDefaults**: Only available for method member.  
  Type: `valueHandleSet <struct depending on signature>`  
  Access Limitation: Read only

- **DefaultResult**: Only available for method member.  
  Type: `valueHandleSet <return type>`  
  Access Limitation: Read only

- **AutoAnswerMode**: Only available for method member.  
  Type: `valueHandleSet uint32`  
  Access Limitation: Read only

- **AutoAnswerTimeNS**: Only available for method member.  
  Type: `valueHandleSet int64`  
  Access Limitation: Read only

## Example

```plaintext
// vCDL
version 1.4;
namespace SomeNamespace
{
  [Binding="Abstract", AutoSubscribe=false]
  interface SomeInterface 
  {
    consumed data int32 SomeData;
  }
  SomeInterface SomeObject;
  reverse<SomeInterface> OtherObject;
}

// CAPL
on start 
{
  char str[100];
  getAttribute(SomeInterface.SomeData, _SystemAttributes::Binding, str);
  write("Binding: %s", str);
}
on key 'a'
{
  SomeObject.SomeData.subscribe();
}
on key 'b'
{
  $OtherObject.SomeData += 1;
}
on any_value_update SomeInterface.SomeData
{
  write("value of %s.SomeData updated to %d", this.object.Path, $this.value);
}
on any_value_update SomeInterface.SomeData.SubscriptionState
{
  write("subscription state of %s.SomeData updated", this.object.Path);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
