[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINStopDisturbance.md)

## linStopDisturbance

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linStopDisturbance

### Function Syntax

```plaintext
long linStopDisturbance();
```

### Description

Stops the disturbance on the bus which is started with [linStartDisturbance()](CAPLfunctionLINStartDisturbance.md).

Note that disturbances shorter than 64 bit times cannot be stopped.

### Parameters

—

### Return Values

On success a value unequal to zero, otherwise zero.

### Example

—

[linStartDisturbance](CAPLfunctionLINStartDisturbance.md)
