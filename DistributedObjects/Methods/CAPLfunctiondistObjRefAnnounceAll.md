[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjRefAnnounceAll.md)

**CAPL Functions** » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjRef::AnnounceAll

# distObjRef::AnnounceAll

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

void [distObjRef](../Objects/CAPLfunctiondistObjRef.md)::AnnounceAll();

## Description

This is a collective operation that announces all provided members which use the publish-subscribe pattern with announcements.

## Parameters

—

## Return Values

—

## Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  object.AnnounceAll();
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)