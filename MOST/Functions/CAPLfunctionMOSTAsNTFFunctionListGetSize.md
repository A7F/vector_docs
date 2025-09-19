[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsNTFFunctionListGetSize.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsNtfFunctionListGetSize, mostAsNtfFunctionListGetFunction

# mostAsNtfFunctionListGetSize, mostAsNtfFunctionListGetFunction

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostAsNtfFunctionListGetSize(long deviceID, 
 long fblockID, long instID);
```

```
long mostAsNtfFunctionListGetFunction(long deviceID, 
 long fblockID, long instid, long index);
```

## Description

The function makes it possible to output the list of all functions in which the notification client (deviceID) is registered. Functionality is similar to command message FBlock.NotificationCheck.Get(deviceID).

The notification matrix can be read out with the function without sending a respective message.

## Parameters

- **deviceID**: Address of the notification client. Exception: -1 outputs a list of all enabled functions.
- **fblockID**: Function block ID
- **instID**: Instance ID
- **index**: Index in the function list

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostAsNtfFunctionCheck](CAPLfunctionMOSTAsNTFFunctionCheck.md) • [mostAsNtfDeviceIDListGetSize, mostAsNtfDeviceIDListGetDeviceID](CAPLfunctionMOSTAsNTFDeviceIDListGetSize.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
