# distObjMemberRef::Announce

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjMemberRef::Announce

**Valid for**: [CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
void distObjMemberRef::Announce();
```

## Description

Announces the member. This method is only available for provided data/event/field members which use the publish-subscribe pattern with announcements.

## Parameters

—

## Return Values

—

## Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  object.ExampleEvent.Announce();
}
```
