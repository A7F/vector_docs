[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetShutdownFlag.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetShutdownFlag

# mostGetShutdownFlag

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostGetShutdownFlag(long channel);
```

## Description

Returns the current state of the Shutdown flag.

## Parameters

- **channel**: Application channel number.

## Return Values

- **1**: Shutdown Flag set.
- **0**: Shutdown Flag not set.
- **< 0**: MOST CAPL [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—
