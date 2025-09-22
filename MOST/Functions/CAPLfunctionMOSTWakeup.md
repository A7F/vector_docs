[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTWakeup.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostWakeup

# mostWakeup

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostWakeup (long channel, long duration);
```

## Description

The function wakes up the MOST loop optically by switching on the light on the output of the connected MOST hardware for the maximum duration.

## Parameters

- **channel**: Channel of the connected MOST hardware
- **duration**: Length of the wake-up impulse [ms]

## Return Values

- **\<= 0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostSetTxLight](CAPLfunctionMOSTSetTxLight.md) • [mostGetTxLight](CAPLfunctionMOSTGetTxLight.md) • [on mostLightLockError](../EventProcedures/CAPLfunctionOnMOSTLightLockError.md) • [mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetCorrectStartupSBC](CAPLfunctionMOSTSetCorrectStartupSBC.md) • [mostShutDown](CAPLfunctionMOSTShutDown.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
