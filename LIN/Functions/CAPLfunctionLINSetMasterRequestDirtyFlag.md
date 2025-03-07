# linSetMasterRequestDirtyFlag

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetMasterRequestDirtyFlag.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linSetMasterRequestDirtyFlag

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword linSetMasterRequestDirtyFlag (dword dirty);
```

## Description

Sets the dirty flag for the LIN master request frame (frame identifier=0x3C). The master request only gets transmitted when the dirty flag is set.

**Note**: The dirty flag also gets set implicitly with every data update on the master request.

## Parameters

- **dirty**  
  - 0: clear the dirty flag
  - 1: set the dirty flag

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)