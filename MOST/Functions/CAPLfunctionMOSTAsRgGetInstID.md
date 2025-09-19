[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsRgGetInstID.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsRgGetInstID

# mostAsRgGetInstID

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long mostAsRgGetInstID(long regsel, long i);
```

## Description

Returns the InstID at position i of the registry. Indexing starts at 0.

## Parameters

- **regsel**
  - 1: Local FBlockList
  - 2: Bus registry

- **i**
  - Position of the registry entry.

## Return Values

- **>=0**
  - InstID

- **<0**
  - See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostAsRgGetSize](CAPLfunctionMOSTAsRgGetSize.md)  •  [OnMostAsRegistry](../EventProcedures/CAPLfunctionOnMOSTAsRegistry.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
