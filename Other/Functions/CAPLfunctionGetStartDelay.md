[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetStartDelay.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getStartdelay

# getStartdelay

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`int getStartdelay();`

## Description

Determines the value of the start delay configured for this network node in the Simulation Setup.

## Parameters

—

## Return Values

Start delay in ms. If no start delay was set the function returns the value zero.

## Example

```c
int val;
...
// Assign to val the value of the start delay
val = getStartdelay();
...
```

[setStartdelay](CAPLfunctionSetstartdelay.md)
