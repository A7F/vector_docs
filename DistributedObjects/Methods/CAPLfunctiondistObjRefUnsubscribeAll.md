[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjRefUnsubscribeAll.md)

## CAPL Functions » Distributed Objects » distObjRef::UnsubscribeAll

### distObjRef::UnsubscribeAll

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Method Syntax

```plaintext
void distObjRef::UnsubscribeAll();
```

### Description

This is a collective operation that unsubscribes all consumed members which use the publish-subscribe pattern.

### Parameters

—

### Return Values

—

### Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  object.UnsubscribeAll();
}
```
