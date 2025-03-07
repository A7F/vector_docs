[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetPrimitiveData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetPrimitiveData, diagSetPrimitiveData

# diagGetPrimitiveData, diagSetPrimitiveData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagGetPrimitiveData (diagResponse obj, byte* buffer, DWORD buffersize)`
- `long diagGetPrimitiveData (diagRequest obj, byte* buffer, DWORD buffersize)`
- `long diagSetPrimitiveData (diagResponse obj, byte* buffer, DWORD buffersize)`
- `long diagSetPrimitiveData (diagRequest obj, byte* buffer, DWORD buffersize)`

## Method Syntax

- `diagResponse::GetPrimitiveData (byte* buffer, DWORD buffersize)`
- `diagRequest::GetPrimitiveData (byte* buffer, DWORD buffersize)`
- `diagResponse::SetPrimitiveData (byte* buffer, DWORD buffersize)`
- `diagRequest::SetPrimitiveData (byte* buffer, DWORD buffersize)`

## Description

Reads/sets the raw data of the complete service primitive (all data that is transmitted via the transport protocol). When setting the data the length of the primitive is not changed.

## Parameters

- **objxt**: Diagnostics object
- **buffer**: Input/output buffer
- **buffersize**: Buffer size

## Return Values

Number of bytes copied into the buffer or [error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```c
// Print the length and first byte of a diagnostic request object
PrintDiagRequestBytes(diagRequest * req)
{
    BYTE primitiveRaw[4095];
    long size;
    size = DiagGetPrimitiveData(req, primitiveRaw, elcount(primitiveRaw));
    if(size > 0)
        write("Request = (%d)[%02x ...]", size, primitiveRaw[0]);
    else
        write("Request: error %d", size);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)