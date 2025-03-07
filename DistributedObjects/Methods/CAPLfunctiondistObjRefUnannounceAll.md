[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjRefUnannounceAll.md)

## CAPL Functions » Distributed Objects » distObjRef::UnannounceAll

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)