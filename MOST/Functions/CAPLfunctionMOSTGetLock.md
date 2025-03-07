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
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostGetLockEx](CAPLfunctionMOSTGetLockEx.md) • [mostSetTxLight](CAPLfunctionMOSTSetTxLight.md) • [mostGetTxLight](CAPLfunctionMOSTGetTxLight.md) • [on mostLightLockError](../EventProcedures/CAPLfunctionOnMOSTLightLockError.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)