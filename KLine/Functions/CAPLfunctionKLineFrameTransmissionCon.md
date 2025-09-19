[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineFrameTransmissionCon.md)

**CAPL Functions** » [K-Line](../CAPLfunctionsKLineOverview.md) » _KLine_FrameTransmissionCon

# _KLine_FrameTransmissionCon

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

_KLine_FrameTransmisionCon(BYTE data[], int64 timestamps[])

## Description

Is called when a frame has been transmitted.

## Parameters

- **data**: Transmitted data buffer of the frame.
- **timestamps**: End of byte time stamps of the transmitted data bytes.

## Return Values

—

## Example

```c
_KLine_FrameTransmissionCon(BYTE data[], int64 timestamps[])
{
    int i;
    int64 p4Time;
    dword systemBaudRate;
    int64 byteLength_ns;
    systemBaudRate  = 10400;
    byteLength_ns = ((1.0/systemBaudRate) * 10) * 1000000000; // 10 bit times in ns

    // Calculate P4 Times
    for (i = 0; i < elcount(data)-1; ++i)
    {
        p4Time = (timestamps[i+1] - byteLength_ns) - timestamps[i];
        write("P4 time between byte no.: %d; Value: %x and byte no.: %d; Value: %x == [%.6f s]\n ", i, data[i], i+1, data[i+1], p4Time/1000000000.0);
    }
}
```

[**_KLine_ByteReceptionInd**](CAPLfunctionKLineByteReceptionInd.md) • [**_KLine_ByteTransmissionCon**](CAPLfunctionKLineByteTransmissionCon.md) • [**_KLine_FrameReceptionInd**](CAPLfunctionKLineFrameReceptionInd.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
