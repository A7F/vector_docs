# Reset

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » Reset

**Valid for**: CANoe DE

**Note**  
This CAPL function is also available in C#.

## Function Syntax

**C#**  
`void Reset.Call();`

**CAPL**  
`void Reset.Call();`

## Description

Calling this function resets the values of the available sensors to their default values and clears the list of objects detected by them. Furthermore, the GroundTruth objects are also set to their default values.

## Parameters

—

## Return Values

—

## Example

### CAPL

`ADASDataManager.Reset.Call();`

### C#

`ADASDataManager.Reset.Call();`
