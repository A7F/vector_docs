# TestMostReadReg

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
long TestMostReadReg(long aChannel, long aChip, dword aOffset, dword aRegDataLen, unsigned long aTimeout);
```

## Description

Reads one or several chip registers in the MOST hardware and waits for the result. If the operation is successful, the written register values can be read out using [TestMostRegGetData](CAPLfunctionTestMostRegGetData.md).

## Parameters

- **aChannel**: Channel connected to the hardware.
- **aChip**: MOST hardware chip ID. Possible values are:
  - 1 : OS814 (other chips cannot be accessed as of yet)
- **aOffset**: First register address.
- **aRegDataLen**: Number of registers to be read. Values between 1 and 16 are possible.
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout monitoring; test module waits infinitely long)

## Return Values

- **-101 to -129**: Error codes like for [mostReadReg](../../MOST/Functions/CAPLfunctionMOSTReadReg.md), [mostWriteReg](../../MOST/Functions/CAPLfunctionMOSTWriteReg.md)
- **-2**: Resume based on Constraint Violation
- **-1**: General error e.g. the functionality is not available
- **0**: Resume based on Timeout

Resume based on occurred event

## Example

—

[TestMostWriteReg](CAPLfunctionTestMostWriteReg.md) • [TestMostRegGetData](CAPLfunctionTestMostRegGetData.md)
