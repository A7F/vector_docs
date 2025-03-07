[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjMemberRefUnsubscribe.md)

**CAPL Functions** » **Distributed Objects** » **distObjMemberRef::Unsubscribe**

# distObjMemberRef::Unsubscribe

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

void [distObjMemberRef](../Objects/CAPLfunctiondistObjMemberRef.md)::Unsubscribe();

## Description

Unsubscribes the member. This method is only available for consumed data/event/field members which use the publish-subscribe pattern.

## Parameters

—

## Return Values

—

## Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  object.ExampleEvent.Unsubscribe();
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)