# distObjRef::SubscribeAll

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

void [distObjRef](../Objects/CAPLfunctiondistObjRef.md)::SubscribeAll();

## Description

This is a collective operation that subscribes all consumed members which use the publish-subscribe pattern.

## Parameters

—

## Return Values

—

## Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  object.SubscribeAll();
}
```
