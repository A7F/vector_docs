[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjEventRefTrigger.md)

## distObjEventRef::Trigger

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjEventRef::Trigger

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Method Syntax

```plaintext
void distObjEventRef::Trigger();
```

### Description

Triggers an update event on the member value. This method is only available for event members with type void.

### Parameters

—

### Return Values

—

### Example

```plaintext
on start
{
  ExampleObject.ExampleEvent.Trigger();
}

on value_update ExampleObject.ExampleEvent
{
  write("Update");
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)