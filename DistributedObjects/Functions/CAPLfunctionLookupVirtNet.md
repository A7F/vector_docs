[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Functions/CAPLfunctionLookupVirtNet.md)

# lookupVirtNet

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » lookupVirtNet

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
virtNet lookupVirtNet(char path[]);
```

## Description

Obtains a virtual network by using a string.

## Parameters

- **path**: Fully qualified name of the virtual network.

## Return Values

- Virtual network with the given path.
- Invalid virtual network if nothing was found.

## Example

```plaintext
// vCDL
version 1.3;
namespace SomeNamespace {
  virtualnetwork VN;
}

// CAPL
on key 'a' {
  DoSomething(lookupVirtNet("SomeNamespace::VN"));
}

void DoSomething(virtNet p) {}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)