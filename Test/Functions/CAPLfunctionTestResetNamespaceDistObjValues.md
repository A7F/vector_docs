[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestResetNamespaceDistObjValues.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestResetNamespaceDistObjValues

# TestResetNamespaceDistObjValues

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestResetNamespaceDistObjValues (char aNamespace[]);
```

## Description

Resets the values of all members of all distributed objects in a namespace to their initial values. In contrast to [resetDistObjValues](../../DistributedObjects/Functions/CAPLfunctionResetDistObjValues.md), information about the operation is written into the test report.

## Parameters

- **aNamespace**: The namespace. It must be fully qualified, i.e., include all parent namespaces.

## Return Values

- **0**: Success
- **-1**: Error, e.g., namespace not found

## Example

### CAPL

```plaintext
void MainTest()
{
  Write("%d", $SomeObject.i);
  $SomeObject.i = 100;
  Write("%d", $SomeObject.i);
  TestResetNamespaceDistObjValues("myNamespace");
  Write("%d", $SomeObject.i);
}
```

### vCDL

```vcdl
version 1.4;
namespace myNamespace {
  object SomeObject {
    internal data int32 i = 42;
  }
}
```

[TestResetNamespaceSysVarValues](CAPLfunctionTestResetNamespaceSysVarValues.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)