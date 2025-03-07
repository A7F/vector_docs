[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestMostRegGetData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestMostRegGetData

# TestMostRegGetData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long TestMostRegGetData(BYTE aBuffer[], long aBufferSize);
```

## Description

The TestMostRegGetData() function is used together with the [TestMostReadReg](CAPLfunctionTestMostReadReg.md) and [TestMostWriteReg](CAPLfunctionTestMostWriteReg.md) functions.

After initiating one of these two functions, the resulting register value can be copied into a byte buffer. Ensure that the buffer size is as specified. A maximum of 16 bytes are transported with the MostReg result.

Note that the register values are only held ready for call-up until the next wait condition in the test program.

## Parameters

- **aBuffer[]**: Data buffer in which the register values are written
- **aBufferSize**: Size of the given data buffer (max. 16 bytes)

## Return Values

- **-2**: Resume based on Constraint Violation
- **-1**: General error e.g. the functionality is not available
- **0**: Resume based on Timeout
- **1**: Resume based on occurred event

## Example

—

[TestMostReadReg](CAPLfunctionTestMostReadReg.md) • [TestMostWriteReg](CAPLfunctionTestMostWriteReg.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)