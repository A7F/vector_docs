[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanSetChannelMode.md)

## canSetChannelMode

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » canSetChannelMode

**Valid for:** CANoe DE • CANoe:lite DE

### Note

This function can only be used with Vector drivers. The `vcndrvms.DLL` must be at least Version 4.2.40.

### Function Syntax

```plaintext
long canSetChannelMode(long channel, long gtx, long gtxreq);
```

### Description

Activates/deactivates the TXRQ and Tx of the CAN controller. This function does nothing with the Ack bit.

### Parameters

- **channel**: CAN channel
- **gtx**:
  - `0`: tx off
  - `1`: tx on
- **gtxreq**:
  - `0`: gtxreq off
  - `1`: gtxreq on

### Return Values

- **0**: ok
- **!=0**: error

### Example

```plaintext
on key 't'
{
   long channel = 2;
   char gtx = 1;
   char gtxreq = 1;
   canSetChannelMode(channel, gtx, gtxreq);
   Write("Mode set to tx=%d, txreq=%d", gtx, gtxreq);
}
```

[canSetChannelAcc](CAPLfunctionCanSetChannelAcc.md) • [canSetChannelOutput](CAPLfunctionCanSetChannelOutput.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
