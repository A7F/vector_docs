[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsNTFFunctionCheck.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsNtfFunctionCheck

# mostAsNtfFunctionCheck

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostAsNtfFunctionCheck(long deviceID, long fblockID, 
 long instID, long functionID);
```

## Description

Checks whether a notification client (deviceID) is registered in the notification matrix for a function.

## Parameters

- **deviceID**: Address of the notification client
- **fblockID**: Function block ID
- **instID**: Instance ID
- **functionID**: Function ID

## Return Values

- **0**: deviceID is not registered
- **1**: deviceID is registered
- **Other values**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostAsNtfFunctionListGetSize, mostAsNtfFunctionListGetFunction](CAPLfunctionMOSTAsNTFFunctionListGetSize.md) • [mostAsNtfDeviceIDListGetSize, mostAsNtfDeviceIDListGetDeviceID](CAPLfunctionMOSTAsNTFDeviceIDListGetSize.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
