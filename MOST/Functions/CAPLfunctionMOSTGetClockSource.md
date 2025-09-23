[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetClockSource.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetClockSource

# mostGetClockSource

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2610.

## Function Syntax

```
long mostGetClockSource(long channel);
```

## Description

Returns the clock source for the MOST timing master.

## Parameters

- **channel**: Channel of the connected interface

## Return Values

- **0**: Internal oscillator.
- **1**: Synchronizes the timing master clock to the S/PDIF input signal. The network interface must be configured as S/PDIF timing slave.
- **\<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostSetTimingMode](CAPLfunctionMOSTSetTimingMode.md) • [mostSetSyncSpdifMode](CAPLfunctionMOSTSetSyncSpdifMode.md) • [mostGetSyncSpdifMode](CAPLfunctionMOSTGetSyncSpdifMode.md) • [mostSetClockSource](CAPLfunctionMOSTSetClockSource.md) • [mostSetSyncAudio](CAPLfunctionMOSTSetSyncAudio.md) • [mostSetSyncSpdif](CAPLfunctionMOSTSetSyncSpdif.md)
