# distObjRef::Connect

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjRef::Connect

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

void [distObjRef](../Objects/CAPLfunctiondistObjRef.md)::Connect();

## Description

This is a collective operation that connects every member of the object with its virtual network.

## Parameters

—

## Return Values

—

## Example

```plaintext
on start
{
  distObjRef * object = ExampleObject;
  object.Connect();
}
```
