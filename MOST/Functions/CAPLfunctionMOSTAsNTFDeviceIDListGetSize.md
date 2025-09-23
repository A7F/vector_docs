[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsNTFDeviceIDListGetSize.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsNtfDeviceIDListGetSize, mostAsNtfDeviceIDListGetDeviceID

# mostAsNtfDeviceIDListGetSize, mostAsNtfDeviceIDListGetDeviceID

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long mostAsNtfDeviceIDListGetSize(long fblockID, 
 long instID, long functionID);
```

```plaintext
long mostAsNtfDeviceIDListGetDeviceID(long fblockID, 
 long instID, long functionID, long index);
```

## Description

The function makes it possible to output the list of all notification clients registered with the function (functionID). Functionality is similar to command message FBlock.Notification.Get(functionID).

The notification matrix can be read out with the function without sending a respective message.

## Parameters

- **fblockID**: Function block ID
- **instID**: Instance ID
- **functionID**: Function ID
- **index**: Index in the function list

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostAsNtfFunctionCheck](CAPLfunctionMOSTAsNTFFunctionCheck.md) • [mostAsNtfFunctionListGetSize, mostAsNtfFunctionListGetFunction](CAPLfunctionMOSTAsNTFFunctionListGetSize.md)
