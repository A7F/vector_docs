[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINtpErrorInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » LINtp_ErrorInd

# LINtp_ErrorInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void LINtp_ErrorInd(int errorcode);
```

## Description

Callback in case of a LIN-TP error.

## Parameters

- **errorcode**: LIN-TP transport protocol error code.

## Return Values

—

## Example

```plaintext
/*@@caplFunc:LINtp_ErrorInd(int):*///callback
LINtp_ErrorInd(int error)
{
}
/*@@end*/
```
