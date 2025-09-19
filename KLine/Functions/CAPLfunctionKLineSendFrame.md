[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineSendFrame.md)

[CAPL Functions](../../CAPLfunctions.md) » [K-Line](../CAPLfunctionsKLineOverview.md) » KLine_SendFrame

# KLine_SendFrame

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long KLine_SendFrame( byte data[], dword count)
```

## Description

Send data on the active K-Line communication channel. The K-Line header is generated automatically due to header settings.

**Note**: In a tester node, you can achieve this functionality by setting the diagnostics request to the byte sequence directly (with [DiagResize](../../Diagnostics/Functions/CAPLfunctionDiagResize2.md) and [DiagSetPrimitiveData](../../Diagnostics/Functions/CAPLfunctionDiagGetPrimitiveData.md)).

## Parameters

- **data**: Data buffer
- **dword count**: Length of data buffer

## Return Values

On success 0, otherwise a value less than 0.

## Example

```c
_Diag_DataRequest( BYTE data[], dword count, long furtherSegments)
{
   long status;
   status = KLine_SendFrame( data, count);
   write( "KLine_SendFrame returns %d for sending %d bytes", status, count);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
