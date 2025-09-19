# on any_monitored_value_change

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
on any_monitored_value_change <value set>;
```

## Description

This handler is called whenever a value of the given set is changed at a monitoring object. The sets are defined by the DO interface members (e.g. `SomeInterface.SomeData`, `SomeInterface.SomeData.SubscriptionState`). Each value at a derived monitoring object is part of such a set.

## Selectors

- **Selector:** object  
  **Type:** monitoringDistObjRef `<T>`  
  **Access Limitation:** Read only

- **Selector:** value  
  **Type:** valueHandle `<T>`  
  **Access Limitation:** Read only

## Example

```c
// vCDL
version 1.4;
namespace SomeNamespace {
  [Binding="Abstract"]
  interface SomeInterface {
    provided data int32 SomeMember;
  }
  SomeInterface ProvidingObject;
  reverse<SomeInterface> ConsumingObject;

  [Monitoring] SomeInterface MonitoringObject;
}

// CAPL
on key 'a' {
  $ProvidingObject.SomeMember = 42;
}
on any_monitored_value_change SomeInterface.SomeMember {
  Write("SomeMember at monitoring object %s has value %d", this.object.Path, $this.value);
}
```
