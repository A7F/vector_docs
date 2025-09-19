[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTWriteReg.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostWriteReg

# mostWriteReg

Valid for:  CANoe DE

**Note**

Changes to registers may lead to unpredictable behavior of the network interface.

**Register layout of the OS8104:**

The registers of the OS8104 chip are distributed among pages. It is not possible to perform read or write actions on register pages. The offset is calculated as follows: offset = page << 8 + address

## Function Syntax

```plaintext
long mostWriteReg(long channel, long chip, dword offset, long regdatalen, byte regdata[]);
```

## Description

Writes to one or more registers of a MOST hardware chip.

## Parameters

- **channel**: Channel to which the hardware is connected
- **chip**: Number of the MOST hardware chip (1 = OS8104; other chips cannot be accessed yet)
- **offset**: Address of the first register
- **regdatalen**: Number of registers to be written (maximum 16)
- **regdata[]**: A byte buffer at least regdatalen in size with the data to be written

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostReadReg](CAPLfunctionMOSTReadReg.md) • [OnMostReg](../EventProcedures/CAPLfunctionOnMOSTReg.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
