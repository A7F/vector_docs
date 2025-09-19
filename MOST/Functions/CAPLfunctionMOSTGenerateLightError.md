[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGenerateLightError.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGenerateLightError

# mostGenerateLightError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This functionality is available for VN2600/VN2610/VN2640 hardware and OptoLyzerOL3150o (firmware version >= V1.5.3).

## Function Syntax

```
long mostGenerateLightError(long channel, long lightofftime, long lightontime, long repeat);
```

## Description

Starts (repeat > 0) or stops (repeat = 0) generation of Light-ON-OFF transitions.

For OptoLyzerOL3150o: The stress network interface controller (NIC) must have **active bypass** or **bypass opened** (see [mostSetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md)).

## Parameters

- **channel**: Channel of the connected interface.
- **lightofftime**: Time during which no light is emitted (in ms).
- **lightontime**: Time during which modulated light is emitted (in ms).
- **repeat**:
  - `0`: Stop Light-Off-On transitions
  - `>0`: Number of Light-Off-On transitions
  - `0xFFFF`: Generate Light-Off-On transitions continually

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGenerateBusloadAsync](CAPLfunctionMOSTGenerateBusloadAsync.md) • [mostGenerateBusloadCtrl](CAPLfunctionMOSTGenerateBusloadCtrl.md) • [mostGenerateLockError](CAPLfunctionMOSTGenerateLockError.md) • [OnMostStress](../EventProcedures/CAPLfunctionOnMOSTStress.md) • [mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [on mostLightLockError](../EventProcedures/CAPLfunctionOnMOSTLightLockError.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
