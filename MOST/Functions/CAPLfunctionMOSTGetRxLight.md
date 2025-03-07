[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetRxLight.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetRxLight

# mostGetRxLight

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostGetRxLight(long channel);
```

## Description

Queries the Light Status at the Fiber Optical Receiver (FOR).

## Parameters

- **channel**: Channel of the interface to be queried.

## Return Values

- **1**: Light on
- **0**: Light out
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetTxLight](CAPLfunctionMOSTSetTxLight.md) • [mostGetTxLight](CAPLfunctionMOSTGetTxLight.md) • [on mostLightLockError](../EventProcedures/CAPLfunctionOnMOSTLightLockError.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)