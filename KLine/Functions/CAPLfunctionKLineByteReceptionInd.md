[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineByteReceptionInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [K-Line](../CAPLfunctionsKLineOverview.md) » _KLine_ByteReceptionInd

# _KLine_ByteReceptionInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

_KLine_ByteReceptionInd(BYTE byteIn, int64 endOfByteTimes_ns)

## Description

Is called when a byte has been received.

## Parameters

- **byteIn**: Received byte
- **endOfByteTimes_ns**: End of byte time stamp in ns resolution.

## Return Values

—

## Example

```plaintext
_KLine_ByteReceptionInd(BYTE byteIn, int64 endOfByteTimes_ns)
{
   int64 endOfByteCorrection_ns;
   dword systemBaudRate;
   float uartSamplePoint;
   systemBaudRate  = 10400;
   uartSamplePoint = 0.5;
   write("Byte Value: %x", byteIn);
   write("End of Byte Time: [%.9f]", endOfByteTimes_ns/1000000000.0);
   // UART sample point corrected end of byte time. UART samples in the middle of a bit.
   endOfByteCorrection_ns = ((1.0/systemBaudRate) * uartSamplePoint) * 1000000000;
   write("Corrected End of Byte Time: [%.9f]", (endOfByteTimes_ns + endOfByteCorrection_ns)/1000000000.0);
}
```

[_KLine_ByteTransmissionCon](CAPLfunctionKLineByteTransmissionCon.md) • [_KLine_FrameReceptionInd](CAPLfunctionKLineFrameReceptionInd.md) • [_KLine_FrameTransmissionCon](CAPLfunctionKLineFrameTransmissionCon.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
