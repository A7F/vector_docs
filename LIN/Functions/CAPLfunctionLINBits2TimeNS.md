[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINBits2TimeNS.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linBits2Time_ns

# linBits2Time_ns

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
int64 linBits2Time_ns(dword bitTimes);
int64 linBits2Time_ns(dword channel, dword bitTimes);
```

## Description

Converts specified bit time to an absolute time. The absolute time is calculated using the current baudrate on the channel determined by the CAPL program context.

## Parameters

- **bitTimes**: Time in bits.
- **channel**: Channel number, whose baudrate will be used.

## Return Values

Absolute time in ns.

## Example

Convert header bit time of a LIN frame to ns

```plaintext
on linFrame *
{
    int64 headerTimeInNanoSeconds; // time in ns
    headerTimeInNanoSeconds = linBits2Time_ns(this.LIN_HeaderTime);
}
```

[linTime2Bits_ns](CAPLfunctionLINTime2BitsNS.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
