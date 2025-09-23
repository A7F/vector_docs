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

- **\<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)
- **0**: No result available
- **1**: No fault saved
- **2**: Failure ‘Sudden Signal Off’
- **3**: Failure ‘Critical Unlock’

## Example

—

[OnMostShutdownReason](../EventProcedures/CAPLfunctionOnMostShutdownReason.md) • [mostSetShutdownReason](CAPLfunctionMOSTSetShutdownReason.md)
