[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetSystemLock.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetSystemLock

# mostGetSystemLock

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostGetSystemLock(long channel);
```

## Description

Returns the current state of the System Lock Flag.

## Parameters

- **channel**: Application channel number.

## Return Values

- **1**: System Lock Flag set
- **0**: System Lock Flag not set
- **< 0**: MOST CAPL [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
