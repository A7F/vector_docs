[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetShutdownReason.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetShutdownReason

# mostGetShutdownReason

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostGetShutdownReason(long channel);
```

## Description

Retrieves the last shutdown reason value.

## Parameters

- **channel**: Channel of the connected interface.

## Return Values

- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)
- **0**: No result available
- **1**: No fault saved
- **2**: Failure ‘Sudden Signal Off’
- **3**: Failure ‘Critical Unlock’

## Example

—

[OnMostShutdownReason](../EventProcedures/CAPLfunctionOnMostShutdownReason.md) • [mostSetShutdownReason](CAPLfunctionMOSTSetShutdownReason.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
