[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionReset.md)

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)