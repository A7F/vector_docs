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
