[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsNTFFunctionClearAll.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsNtfFunctionClearAll

# mostAsNtfFunctionClearAll

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostAsNtfFunctionClearAll(long deviceID, long fblockID, long instID;
```

## Description

Clears notification client entries from the notification matrix (deviceID >= 0). Functionality is similar to command message FBlock.Notification.Set(ClearAll, deviceID). The notification matrix can be written with the function without sending a respective message.

## Parameters

- **deviceID**: Address of the notification client. Exception: -1 clears the entire notification matrix.
- **fblockID**: Function block ID.
- **instID**: Instance ID.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostAsNtfFunctionSet](CAPLfunctionMOSTAsNTFFunctionSet.md) • [mostAsNtfFunctionClear](CAPLfunctionMOSTAsNTFFunctionClear.md)
