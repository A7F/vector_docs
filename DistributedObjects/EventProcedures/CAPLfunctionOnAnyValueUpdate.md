[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/EventProcedures/CAPLfunctionOnAnyValueUpdate.md)

**CAPL Functions** » **Distributed Objects** » **on any_value_update**

# on any_value_update

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
on any_value_update <value set>;
```

## Description

This handler is called whenever a value of the given set is updated. The sets are defined by the DO interface members (e.g. `SomeInterface.SomeData`, `SomeInterface.SomeData.SubscriptionState`). Each value at a derived object is part of such a set.

## Parameters

- **<value set>**: Designates the value set for which the handler shall be called.

## Selectors

- **Selector**: object
  - **Type**: distObjRef <T>
  - **Access Limitation**: Read only

- **Selector**: value
  - **Type**: valueHandle <T>
  - **Access Limitation**: Read only

## Example

```plaintext
// vCDL
version 1.4;
namespace SomeNamespace
{
  interface SomeInterface
  {
    internal data int32 SomeData;
  }
  SomeInterface Obj1;
  SomeInterface Obj2;

// CAPL requires named interfaces for use in handlers
  typedef SomeInterfaceRev = reverse<SomeInterface>;
  SomeInterfaceRev Obj3;
}

// CAPL
on key 'a'
{
  $Obj1.SomeData = 42;
}
on key 'b'
{
  $Obj2.SomeData = 42;
}
on key 'c'
{
  $Obj3.SomeData = 42;
}

// helper function to compare DOs by identity
dword equals(distObjRef * a, distObjRef * b)
{
  if (!a.IsValid || !b.IsValid)
    return 0;
  return strncmp(a.Path, b.Path, _max(elCount(a.Path), elCount(b.Path))) == 0;
}
// handler for Obj1 and Obj2
on any_value_update SomeInterface.SomeData
{
  write("Updated SomeData at object %s to value %d",
  this.object.Path,
  $this.value);
  if (equals(this.object, Obj2))
  {
    write("Specialized code for Obj2");
  }
}
// handler for Obj3
on any_value_update SomeInterfaceRev.SomeData
{
  write("Updated SomeData at object %s to value %d",
  this.object.Path,
  $this.value);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)