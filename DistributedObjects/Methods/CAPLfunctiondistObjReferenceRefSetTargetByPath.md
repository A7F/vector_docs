[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjReferenceRefSetTargetByPath.md)

**CAPL Functions** » **Distributed Objects** » **distObjReferenceRef::SetTargetByPath**

# distObjReferenceRef::SetTargetByPath

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
long distObjReferenceRef *::SetTargetByPath(char path[]);
```

## Description

Sets the target object of the reference.

## Parameters

- **path**: Fully qualified path of the new target object.

## Return Values

- **0**: OK
- **1**: An error occurred

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {
    internal data int32 d;
  }
  object Obj : SomeInterface {}
  reference<SomeInterface> Ref;
}

// CAPL
on key 'a' {
  write("%d", Ref.HasTarget); // output: 0
  Ref.SetTargetByPath("SomeNamespace::Obj");
  write("%d", Ref.HasTarget); // output: 1
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)