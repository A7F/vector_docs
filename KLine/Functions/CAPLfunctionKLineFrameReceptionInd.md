[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineFrameReceptionInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [K-Line](../CAPLfunctionsKLineOverview.md) » _KLine_FrameReceptionInd

# _KLine_FrameReceptionInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

_KLine_FrameReceptionInd(BYTE data[], int64 timestamps[])

## Description

Is called when a frame has been received.

## Parameters

- **data**: Received data buffer of the frame.
- **timestamps**: End of byte time stamps of the received data bytes.

## Return Values

—

## Example

```c
_KLine_FrameReceptionInd(BYTE data[], int64 timestamps[])
{
   int i;
   int64 p1Time;
   dword systemBaudRate;
   int64 byteLength_ns;
   systemBaudRate  = 10400;
   byteLength_ns = ((1.0/systemBaudRate) * 10) * 1000000000; // 10 bit times in ns
   // Calculate P1 Times
   for (i = 0; i < elcount(data)-1; ++i)
   {
      p1Time = (timestamps[i+1] - byteLength_ns) - timestamps[i];
      write("P1 time between byte no.: %d; Value: %x and byte no.: %d; Value: %x == [%.6f]\n ", i, data[i], i+1, data[i+1], p1Time/1000000000.0);
   }
}
```

[Link to _KLine_ByteReceptionInd](CAPLfunctionKLineByteReceptionInd.md) • [Link to _KLine_ByteTransmissionCon](CAPLfunctionKLineByteTransmissionCon.md) • [Link to _KLine_FrameTransmissionCon](CAPLfunctionKLineFrameTransmissionCon.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)