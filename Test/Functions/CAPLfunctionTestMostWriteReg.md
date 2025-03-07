[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestMostWriteReg.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestMostWriteReg

# TestMostWriteReg

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long TestMostWriteReg(long aChannel, long aChip, dword aOffset, dword aRegDataLen, BYTE aRegData[], unsigned long aTimeout);
```

## Description

Writes one or several chip registers in the MOST hardware and waits for the result. If the operation is successful, the written register values can be read out using [TestMostRegGetData](CAPLfunctionTestMostRegGetData.md).

## Parameters

- **aChannel**: Channel connected to the hardware.
- **aChip**: MOST hardware chip ID. Possible values are:
  - 1 : OS814 (other chips cannot be accessed as of yet)
- **aOffset**: First register address.
- **aRegDataLen**: Number of registers to be read (maximum 16 bytes with VN2600/VN2610).
- **aRegData[]**: Data buffer with data to write (minimum size aRegDataLen).
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout monitoring; test module waits infinitely long).

## Return Values

- **-2**: Resume based on Constraint Violation
- **-1**: General error e.g. the functionality is not available
- **0**: Resume based on Timeout
- **1**: Resume based on occurred event

## Example

—

[TestMostReadReg](CAPLfunctionTestMostReadReg.md) • [TestMostRegGetData](CAPLfunctionTestMostRegGetData.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)