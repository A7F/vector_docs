[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/EventProcedures/CAPLfunctionOnAnyMonitoredValueChange .md)

**CAPL Functions** » **Distributed Objects** » **on any_monitored_value_change**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)