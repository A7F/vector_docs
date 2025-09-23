[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetLock.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetLock

# mostGetLock

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostGetLock(long channel);
```

## Description

Queries the Lock Status of the MOST hardware.

## Parameters

- **channel**: Channel of the interface to be queried.

## Return Values

- **1**: Lock
- **0**: Unlock
- **\<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostGetLockEx](CAPLfunctionMOSTGetLockEx.md) • [mostSetTxLight](CAPLfunctionMOSTSetTxLight.md) • [mostGetTxLight](CAPLfunctionMOSTGetTxLight.md) • [on mostLightLockError](../EventProcedures/CAPLfunctionOnMOSTLightLockError.md)
