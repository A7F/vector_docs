# linUpdateResponse

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINUpdateResponse.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linUpdateResponse

## Function Syntax

- `dword linUpdateResponse(dword frameId, dword dlc, byte[] responseData); // form 1`
- `dword linUpdateResponse(linFrame frame); // form 2`

## Description

Updates the response data of a specific LIN frame.

## Parameters

- **frameId**: ID of the LIN frame whose response will be updated. Value range: 0..63
- **dlc**: Number of data bytes contained in the frame (Data Length Code). Value range: 0..8
- **responseData**: An array of bytes which contains the response data to be set.
- **frame**: The LIN frame whose response will be updated.

## Return Values

Returns **1** if the response update succeeded, otherwise **0**.

## Example

```c
// Update the response of the LIN frame with the id 0x04

on linFrame 0x04
{
  long i;
  byte frm4data[8];

  for(i = 0; i < linGetDlc(this.id); i++)
  {
    frm4data[i] = this.byte(i) + 1;
  }

  linUpdateResponse(this.id, linGetDlc(this.id), frm4data);
}
```

[linTransmitHeader](CAPLfunctionLINTransmitHeader.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
