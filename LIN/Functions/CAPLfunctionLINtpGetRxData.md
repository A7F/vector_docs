[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINtpGetRxData.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » LINtp_GetRxData

# LINtp_GetRxData

Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void LINtp_GetRxData(byte data[], long size);
```

## Description

Retrieve data bytes received.

## Parameters

- **data**: Copy bytes into this buffer.
- **size**: Maximum number of bytes to copy.

## Return Values

—

## Example

```plaintext
LINtp_DataInd(long count, DWORD nad)
{
  byte rxBuffer[4096];
  LINtp_GetRxData(rxBuffer, count);
  write("received <%02x ...> from/for node %02x", rxBuffer[0], nad);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
