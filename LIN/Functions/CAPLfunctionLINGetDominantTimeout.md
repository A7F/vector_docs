[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetDominantTimeout.md)

# linGetDominantTimeout

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetDominantTimeout

Valid for: CANoe DE

## Function Syntax

```plaintext
int64 linGetDominantTimeout();
```

## Description

Returns the dominant timeout of the current channel’s transceiver in nanoseconds. If zero, the transceiver does not have any dominant timeout.

## Parameters

—

## Return Values

Returns the dominant timeout of the LINpiggy or zero, if the transceiver does not have any dominant timeout.

## Example

—

[linSetGlobalTimeoutPrevention](CAPLfunctionLINSetGlobalTimeoutPrevention.md)
