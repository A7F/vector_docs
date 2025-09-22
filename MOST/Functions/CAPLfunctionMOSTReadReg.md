[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTReadReg.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostReadReg

# mostReadReg

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
Register structure of the OS8104:  
The registers of the OS8104 chip are distributed among pages. Read and write actions are not possible across several register pages. The offset is calculated as follows: offset = page \<\< 8 + address

## Function Syntax

```
long mostReadReg(long channel, long chip, dword offset, long regdatalen);
```

## Description

Initiates read-out of the registers of a MOST hardware chip.

## Parameters

- **channel**: Channel to which the hardware is connected.
- **chip**: Number of the chip in the MOST hardware (1 = OS8104; other chips cannot be accessed yet).
- **offset**: Address of the first register.
- **regdatalen**: Number of registers to be read (1 \<= regdatalen \<= 16).

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

A read request by `mostReadReg()` causes the CAPL event procedure [OnMostReg](../EventProcedures/CAPLfunctionOnMOSTReg.md) to be called.

## Example

—

[mostWriteReg](CAPLfunctionMOSTWriteReg.md) • [OnMostReg](../EventProcedures/CAPLfunctionOnMOSTReg.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
