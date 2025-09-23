[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjRefDisconnect.md)

## distObjRef::Disconnect

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjRef::Disconnect

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Method Syntax

```plaintext
void distObjRef::Disconnect ();
```

### Description

This is a collective operation that disconnects every member of the object from its virtual network.

### Parameters

—

### Return Values

—

### Example

```plaintext
on start
{
  distObjRef * object = ExampleObject;
  object.Disconnect();
}
```
