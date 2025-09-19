# on any_fct_called

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`on any_fct_called <provided or internal interface method>;`

## Description

This handler is called whenever a provided method of a distributed object derived from the given interface is called. At this time, the automatic answering feature has already set the out parameters and return value to their default values if it is configured.

## Parameters

- **<provided or internal interface method>**: Designates the interface method for which the handler shall be called.

## Selectors

- **Selector**: object
  - **Type**: distObjRef <T>
  - **Access Limitation**: Read only

- **Selector**: context
  - **Type**: callContext <T>
  - **Access Limitation**: Read only

## Example

```plaintext
// vCDL
version 1.4;
namespace SomeNamespace
{
  interface SomeInterface
  {
    internal method void SomeMethod(int32 p);
  }
  SomeInterface Obj1;
  SomeInterface Obj2;
}

// CAPL
on key 'a'
{
  Obj1.SomeMethod.CallAsync(1);
}
on key 'b'
{
  Obj2.SomeMethod.CallAsync(2);
}
on any_fct_called SomeInterface.SomeMethod
{
  write("Called SomeMethod at object %s with parameter %d", this.object.Path, this.context.p);
}
```
