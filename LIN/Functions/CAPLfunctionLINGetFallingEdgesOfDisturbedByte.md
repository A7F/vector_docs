[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetFallingEdgesOfDisturbedByte.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linGetFallingEdgesOfDisturbedByte

# linGetFallingEdgesOfDisturbedByte

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linGetFallingEdgesOfDisturbedByte(int64 fallingEdges[]);
```

## Description

With this function it is possible to retrieve time stamps of all falling edges in the disturbed byte or in the pseudo-byte caused by the last bit inversion.

Note, that prior to calling this function the measurement of the falling edges has to be activated and the bit inversion has to be executed (see [linInvertRespBit](CAPLfunctionLINInvertRespBit.md), [linInvertHeaderBit](CAPLfunctionLINInvertHeaderBit.md)).

## Parameters

- **fallingEdges**: An array which will receive the measured time stamps [in nanoseconds]. The array size is 6. Unused time stamps will be set to 0 (i.e. in case of less than 6 falling edges).

## Return Values

On successful request returns 1, otherwise 0.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
