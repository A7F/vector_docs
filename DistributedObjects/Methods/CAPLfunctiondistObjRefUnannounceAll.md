# distObjRef::UnannounceAll

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Method Syntax

void [distObjRef](../Objects/CAPLfunctiondistObjRef.md)::UnannounceAll();

### Description

This is a collective operation that unannounces all provided members which use the publish-subscribe pattern with announcements.

### Parameters

—

### Return Values

—

### Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  object.UnannounceAll();
}
```
