[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetParameter.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetParameter

# diagGetParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

The behavior of this CAPL function depends on the used parameters.

Possible scenarios:

## Retrieve the value of the numeric parameter

### Function Syntax

- `long diagGetParameter (diagResponse obj, char parameterName[], double output[1])`
- `long diagGetParameter (diagRequest obj, char parameterName[], double output [1])`
- `double diagGetParameter (diagResponse obj, char parameterName[])`
- `double DiagGetParameter (diagRequest obj, char parameterName[])`
- `long diagGetParameter (diagResponse obj, long mode, char parameterName[], double output[1])`
- `long DiagGetParameter (diagRequest obj, long mode, char parameterName[], double output [1])`
- `double diagGetParameter (diagResponse obj, long mode, char parameterName[])`
- `double diagGetParameter (diagRequest obj, long mode, char parameterName[])`

### Method Syntax

- `long diagResponse::GetParameter (char parameterName[], double output[1])`
- `long diagRequest::GetParameter (char parameterName[], double output [1])`
- `long diagResponse::GetParameter (char parameterName[])`
- `long diagRequest::GetParameter (char parameterName[])`
- `long diagResponse::GetParameter (long mode, char parameterName[], double output[1])`
- `long diagRequest::GetParameter (long mode, char parameterName[], double output [1])`
- `long diagResponse::GetParameter (long mode, char parameterName[])`
- `long diagRequest::GetParameter (long mode, char parameterName[])`

### Description

Returns the value of the numeric parameter, either in an output field or as return value (without the possibility of checking the correct function).

### Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier
- **Output**: Output field
- **[mode](../CAPLfunctionsDiagnosticsAccessMode.md)**: Access mode

### Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md) or value of the parameter or 0.0 if this could not be acquired.

### Example

```c
// e.g. used in a Tester module
on diagResponse *
{
  byte data[4096];
  long size;
  double param_value1=0xFF;
  double param_value2=0xFF;
  diagResponse * resp;       // declare response with no concrete interpretation
  size=this.GetPrimitiveSize();             // get length of response
  this.GetPrimitiveData(data, elcount(data));  // copy actual response from "on diagResponse *" into data array
  switch(data[0]) 
  {
    case 0x50:                                // UDS: DiagnosticSessionControl_Process positive Response
      diagInitialize(resp, "DiagnosticSessionControl_Process");
      resp.Resize(size);                           // make sure there is room for the received bytes
      resp.SetPrimitiveData(data, size);           // initialize resp with actual response from data array
      param_value1=diagGetParameter(resp, "diagnosticSessionType");
      param_value2=diagGetParameter(resp, "sessionParameterRecord");
      break;
    case 0x51:                                // UDS: EcuReset_Process positive Response
      diagInitialize(resp, "EcuReset_Process");
      resp.Resize(size);                           // make sure there is room for the received bytes
      resp.SetPrimitiveData(data, size);           // initialize resp with actual response from data array
      param_value1=diagGetParameter(resp, "resetType");
      param_value2=diagGetParameter(resp, "powerDownTime");
      break;
    default:
      break;
  }
  write("Tester: Value of parameter according to chosen interpretation: 0x%x 0x%x %3.0lf %3.0lf",data[0], data[1], param_value1, param_value2);
}
```

## Retrieve the symbolic value of the parameter

### Function Syntax

- `long diagGetParameter (diagResponse obj, char parameterName[], char buffer[], dword buffersize)`
- `long diagGetParameter (diagRequest obj, char parameterName[], char buffer[], dword buffersize)`

### Method Syntax

- `diagResponse::GetParameter (char parameterName[], char buffer[], dword buffersize)`
- `diagRequest::GetParameter (char parameterName[], char buffer[], dword buffersize)`

### Description

Returns the symbolic value of the parameter. This functions for all parameters. The values received can be used for setting the parameter.

### Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier
- **buffer**: Output field
- **buffersize**: Size of the buffer

### Return Values

Number of chars written to buffer or [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

### Example

—

## Retrieve the numeric parameter directly

### Function Syntax

- `double diagGetParameter (diagResponse obj, char parameterName[])`
- `double diagGetParameter (diagRequest obj, char parameterName[])`

### Method Syntax

- `diagResponse::GetParameter (char parameterName[])`
- `diagRequest::GetParameter (char parameterName[])`

### Description

Retrieves numeric parameter directly.

### Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier

### Return Values

Parameter value or [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

### Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)