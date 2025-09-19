[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineDataInd.md)

**CAPL Functions** » **K-Line** » _KLine_DataInd

# _KLine_DataInd

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

_KLine_DataInd(byte data[])

## Description

Called for a received K-Line request.

**Note**

This function models a K-Line TP layer which is required for an ECU simulation.

## Parameters

- **data**: Data buffer.

## Return Values

—

## Example

```c
variables
{
    BYTE cKLine_HandleStartCommunication = 0;
    BYTE cKLine_HandleStopCommunication = 1;
}

_KLine_DataInd(byte data[]) // Receive a request
{
    if (cKLine_HandleStartCommunication && data[0] == 0x81)
    {
        BYTE StartCommunicationResp_raw[3] = { 0xC1, 0xEF, 0x8F };
        _Diag_DataRequest(StartCommunicationResp_raw, elcount(StartCommunicationResp_raw), 0);
    }
    else if (cKLine_HandleStopCommunication && data[0] == 0x82)
    {
        BYTE StopCommunicationResp_raw[1] = { 0xC2 };
        _Diag_DataRequest(StopCommunicationResp_raw, elcount(StopCommunicationResp_raw), 0);
    }
}
```

[_KLine_DataCon](CAPLfunctionKLineDataCon.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
