[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjReferenceRefResetTarget.md)

## CAPL Functions » Distributed Objects » distObjReferenceRef::ResetTarget

### distObjReferenceRef::ResetTarget

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Method Syntax

```plaintext
void distObjReferenceRef *::ResetTarget();
```

### Description

Resets the target object of the reference.

### Parameters

—

### Return Values

—

### Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {
    internal data int32 d;
  }
  object Obj : SomeInterface {}
  reference<SomeInterface> Ref = Obj;
}

// CAPL
on key 'a' {
  write("%d", Ref.HasTarget); // output: 1
  Ref.ResetTarget();
  write("%d", Ref.HasTarget); // output: 0
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
