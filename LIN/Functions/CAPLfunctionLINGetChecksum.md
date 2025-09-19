[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetChecksum.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetChecksum

# linGetChecksum

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `byte linGetChecksum(linFrame linFrame);` form 1
- `byte linGetChecksum(linCSError linCsError);` // form 2

## Description

Returns the checksum of a LIN frame or LIN checksum error. Checksum model (classic/enhanced) is determined automatically.

## Parameters

- **linFrame**: LIN frame object
- **linCsError**: LIN checksum error object

## Return Values

Calculated checksum

## Example

Get the checksum of a received LIN frame with name **myframe**

```plaintext
on linFrame myframe
{
    byte checksum;
    checksum = linGetChecksum(this);
}
// Calculate the checksum of a LIN frame object
...
byte checksum;
// create a LIN frame object
linFrame 0x1 myLinFrame = { dlc = 1, byte(0) = 1 };
// calculate its checksum
checksum = linGetChecksum(myLinFrame);
```

[linSetChecksumError](CAPLfunctionLINSetChecksumError.md) • [linSetManualChecksum](CAPLfunctionLINSetManualChecksum.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
