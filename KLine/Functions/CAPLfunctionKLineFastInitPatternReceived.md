[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineFastInitPatternReceived.md)

[CAPL Functions](../../CAPLfunctions.md) » [K-Line](../CAPLfunctionsKLineOverview.md) » _KLine_FastInitPatternReceived

# _KLine_FastInitPatternReceived

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

_KLine_FastInitPatternReceived(dword TiniL_us, dword TWup_us, int64 timestampTWup)

## Description

Called when a fast init pattern has been received.

Called for the following values:

- **TinL**: 25 ms +- 4 ms
- **TWup**: 50 ms +- 4 ms

## Parameters

- **TiniL_us**: TiniL time in us.
- **TWup_us**: TWup time in us.
- **timestampTWup**: End of fast init pattern timestamp

## Return Values

—

## Example

```plaintext
_KLine_FastInitPatternReceived( dword TiniL_us, dword Twup_us, int64 timestampTwup)
{
   write(FastInitPattern @%.3f received, type %d, TiniL = %d us, Twup = %d us", timestampTwup / cNs2s, type, TiniL_us, Twup_us);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)