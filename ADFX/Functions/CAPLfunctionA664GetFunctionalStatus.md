[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionA664GetFunctionalStatus.md)

[CAPL Functions](../../CAPLfunctions.md) » [AFDX »](../CAPLfunctionsAFDXOverview.md) A664GetFunctionalStatus

# A664GetFunctionalStatus

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

`BYTE A664GetFunctionalStatus (PDU aPDU)`

## Description

This function returns the Functional Status (FS) of an AFDX-PDU (FDS) if the FDS-mode is used. In frameMode, use FS-signals instead.

**Note**: This function is only available in PDU-mode.

## Parameters

- **aPDU**: The AFDX-PDU (FDS) of which the status is to be retrieved.

## Example

Examine the Functional Status of any received FDS:

```plaintext
on PDU * {
  int fs = 0;
  fs = a664GetFunctionalStatus(this);
  writeEx(-3,1, "FS of received PDU %s: %d", this.name, fs);
}
```

[See Also](javascript:void(0);)