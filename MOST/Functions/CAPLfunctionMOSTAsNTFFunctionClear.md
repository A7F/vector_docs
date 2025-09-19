[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsNTFFunctionClear.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsNtfFunctionClear

# mostAsNtfFunctionClear

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostAsNtfFunctionClear(long deviceID, long fblockID, 
long instID, long functionID);
```

## Description

Clears a notification client entry from the notification matrix. Functionality is similar to command message FBlock.Notification.Set(Clear, deviceID, functionID).

The notification matrix can be written with the function without sending a respective message.

## Parameters

- **deviceID**: Address of the notification client
- **fblockID**: Function block ID
- **instID**: Instance ID
- **functionID**: Function ID

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostAsNtfFunctionCheck](CAPLfunctionMOSTAsNTFFunctionCheck.md) • [mostAsNtfFunctionSet](CAPLfunctionMOSTAsNTFFunctionSet.md) • [mostAsNtfFunctionClearAll](CAPLfunctionMOSTAsNTFFunctionClearAll.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
