[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetSpecVersion.md)

# mostGetSpecVersion

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetSpecVersion

**Valid for**: CANoe DE

## Function Syntax

```
long mostGetSpecVersion(long channel);
```

## Description

Returns the applied specification version of a MOST channel.

## Parameters

- **channel**: Application channel number.

## Return Values

- **Version of MOST specification**:
  - `0x0205`: version 2.5
  - `0x0300`: version 3.0

  **Note**: Currently the MOST Specification version depends on the chosen speed grade:

## Example

—
