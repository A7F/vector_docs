[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINtpDataInd.md)

## LINtp_DataInd

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » LINtp_DataInd

### Function Syntax

- `void LINtp_DataInd(long count); // form 1`
- `void LINtp_DataInd(long count, dword NAD); // form 2`

### Description

Callback indicates the reception of data. In a Slave node, the NAD indicates the address of the destination node or `0x7E` if data was sent to a functional group; in a Master, the address of the sending slave.

Use [LINtp_GetRxData](CAPLfunctionLINtpGetRxData.md) to retrieve the data.

### Parameters

- **count**: Number of bytes received.
- **NAD**: Node address of the slave node that is the sender (if called in the master node) or receiver of the data (if called in a slave node).

### Return Values

—

### Example

```c
// Before CANoe 8.5, use this signature:
// LINtp_DataInd(long count) { ... }

// Only in CANoe 8.5 or later
LINtp_DataInd(long count, DWORD nad)
{
  byte rxBuffer[4096];
  LINtp_GetRxData(rxBuffer, count);

  if( nad == 0x7E)
    write( "received functional request of %d byte", count);
  else
    write( "received %d bytes from/for node %02x", count, nad);
}
```
