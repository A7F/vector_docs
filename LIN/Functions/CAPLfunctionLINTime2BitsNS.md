[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINTime2BitsNS.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linTime2Bits_ns

# linTime2Bits_ns

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword linTime2Bits_ns(int64 time):` // form 1
- `dword linTime2Bits_ns(dword channel, int64 time);` // form 2

## Description

This function converts specified system times to bit times. The conversion is done using the current baudrate on the channel determined by the CAPL program context.

**Note:** Calling this function with the explicit channel is only possible from a CAPL program defined in the Measurement Setup.

## Parameters

- **time**: System time to be converted [in ns].
- **channel**: Channel number, whose baudrate will be used.

## Return Values

Resulting bit time.

## Example

Extract sync break length of LIN frames

```plaintext
on linFrame *
{
  dword bitTimeSyncBreak;
  bitTimeSyncBreak = linTime2Bits_ns(this.breakLen);
}
```

[linBits2Time_ns](CAPLfunctionLINBits2TimeNS.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)