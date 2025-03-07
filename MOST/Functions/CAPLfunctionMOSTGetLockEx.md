[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetLockEx.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetLockEx

# mostGetLockEx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostGetLockEx (long channel);
```

## Description

The function returns the lock status of the connected MOST hardware. In contrast to [mostGetLock()](CAPLfunctionMOSTGetLock.md), the additional states "Stable Lock" and "Critical Unlock" are considered according to MOST specification 2.3.

## Parameters

- **channel**: Channel of the connected MOST hardware.

## Return Values

- **0**: Unlock
- **1**: Lock
- **2**: Stable Lock
- **3**: Critical Unlock
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostGetLock](CAPLfunctionMOSTGetLock.md) • [OnMostStableLock](../EventProcedures/CAPLfunctionOnMOSTStableLock.md) • [OnMostCriticalUnlock](../EventProcedures/CAPLfunctionOnMOSTCriticalUnlock.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)