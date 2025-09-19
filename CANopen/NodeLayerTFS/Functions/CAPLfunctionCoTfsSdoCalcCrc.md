# coTfsSDOCalcCrc (Level 1)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword coTfsSDOCalcCrc( byte inValueBuf[], dword valueBufSize );
```

## Description

This function calculates the CRC checksum for a block transfer ([SDO block upload](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/PDOTests.md) or [SDO block download](../../../../CANoeCANalyzer/CANopen/TfsNodelayer/SDO/BlockSdoDownload.md)) - necessary for the calculation of the CRC across several data ranges.

## Parameters

- **inValueBuf[]**: In this data field are the data for which the CRC calculation is executed.
- **valueBufSize**: Buffer size in byte of `inValueBuf`.

## Return Values

CRC checksum

## Example

```c
byte inValueBuf[4] = {0x1, 0x2, 0x3, 0x4};
dword valueBufSize = 4;
dword crc = 0; /* to store the return value of function */

crc = coTfsSDOCalcCrc( inValueBuf, valueBufSize );

/* outputs a message to the 'write' window */
write( "coTfsSDOCalcCrc = %04X", crc);

/* The message will be appeared in report if it is enabled */
/* testStep( "CAPL text", "coTfsSDOCalcCrc = %04X", crc); */
```

[Used Constants](../CAPLfunctionsCANopenNLTFSExampleConstants.md)
