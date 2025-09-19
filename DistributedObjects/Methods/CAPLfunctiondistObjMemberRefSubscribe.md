# distObjMemberRef::Subscribe

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

void [distObjMemberRef](../Objects/CAPLfunctiondistObjMemberRef.md)::Subscribe();

## Description

Subscribes the member. This method is only available for consumed data/event/field members which use the publish-subscribe pattern.

## Parameters

—

## Return Values

—

## Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  object.ExampleEvent.Subscribe();
}
```
