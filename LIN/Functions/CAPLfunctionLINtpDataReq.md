[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINtpDataReq.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » LINtp_DataReq

# LINtp_DataReq

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void LINtp_DataReq(byte data[], long numData, long NAD);
```

## Description

Send the given data. Once all data has been sent, the callback [LINtp_DataCon](CAPLfunctionLINtpDataCon.md) is called. If there has been an error, [LINtp_ErrorInd](CAPLfunctionLINtpErrorInd.md) is called.

## Parameters

- **data**: Data to send.
- **numData**: Number of bytes to send.
- **NAD**: Slave node address

## Return Values

—

## Example

```plaintext
BYTE data[20];
LINtp_DataReq( data, elcount(data), 0x12);
```
