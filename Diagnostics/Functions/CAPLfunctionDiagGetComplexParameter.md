# diagGetComplexParameter

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetComplexParameter.md)

**CAPL Functions** » **Diagnostics** » diagGetComplexParameter

**Valid for**: CANoe DE

The behavior of this CAPL function depends on the used parameters.

Possible scenarios:

## Retrieve the numeric sub-parameter from a parameter iteration

### Function Syntax

- `long diagGetComplexParameter (diagResponse obj, char parameterName[], dword iteration, char* subParameter, double output[1])`
- `long diagGetComplexParameter (diagRequest obj, char parameterName[], dword iteration, char* subParameter, double output[1])`
- `double diagGetComplexParameter (diagResponse obj, char parameterName[], dword iteration, char* subParameter)`
- `double diagGetComplexParameter (diagRequest obj, char parameterName[], dword iteration, char* subParameter)`
- `long diagGetComplexParameter (diagResponse obj, long mode, char parameterName[], dword iteration, char* subParameter, double output[1])`
- `long dDiagGetComplexParameter (diagRequest obj, long mode, char parameterName[], dword iteration, char* subParameter, double output[1])`
- `double diagGetComplexParameter (diagResponse obj, long mode, char parameterName[], dword iteration, char* subParameter)`
- `double diagGetComplexParameter (diagRequest obj, long mode, char parameterName[], dword iteration, char* subParameter)`

### Method Syntax

- `long diagResponse::GetComplexParameter (char* parameterName, dword iteration, char subParameter[], double output[1])`
- `long diagRequest::GetComplexParameter (char* parameterName, dword iteration, char subParameter[], double output[1])`
- `long diagResponse::GetComplexParameter (char parameterName[], dword iteration, char* subParameter)`
- `long diagRequest::GetComplexParameter (char parameterName[], dword iteration, char* subParameter)`
- `long diagResponse::GetComplexParameter (long mode, char parameterName[], dword iteration, char* subParameter, double output[1])`
- `long diagRequest::GetComplexParameter (long mode, char parameterName[], dword iteration, char* subParameter, double output[1])`
- `long diagResponse::GetComplexParameter (long mode, char parameterName[], dword iteration, char* subParameter)`
- `long diagRequest::GetComplexParameter (long mode, char parameterName[], dword iteration, char subParameter[])`

### Description

Retrieve numeric sub-parameter from a parameter iteration directly.

### Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier
- **iteration**: Iteration (beginning with 0)
- **subParameter**: Sub parameter qualifier
- **output**: Output field. If given, `output` contains the value of the parameter after return of this method.
- **mode**: Switch the representation of the transmitted value according to the given [mode](../CAPLfunctionsDiagnosticsAccessMode.md).

### Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md) or value of the parameter or 0.0 if this could not be acquired.

### Example

```plaintext
on diagResponse Door.FaultMemory_ReadAllIdentified
{
  dword DTC;
  char DTCasText[100];
  int i;

  if(diagIsPositiveResponse(this))
  {
    // Iterate over the list of DTCs and retrieve the numeric and symbolic value of each DTC
    for(i=0;i<DiagGetIterationCount(this,"ListOfDTC");i++)
    {
      DTC=DiagGetComplexParameter(this,"ListOfDTC",i,"DTC");
      DiagGetComplexParameter(this,"ListOfDTC", i, "DTC" , DTCasText, elCount(DTCasText));
      write("DTC %06X - %s",DTC, DTCasText);
    }
  }
  else
  {
    write("Negative response received.\nNegative response code: 0x%02X", (byte)DiagGetResponseCode(this));
  }
}
```

## Retrieve the symbolic value of a complex parameter

### Function Syntax

- `long diagGetComplexParameter (diagResponse obj, char parameterName[], dword iteration, char subParameter[], char buffer[], dword buffersize)`
- `long diagGetComplexParameter (diagRequest obj, char parameterName[], dword iteration, char subParameter[], char buffer[], dword buffersize)`

### Method Syntax

- `diagResponse.GetComplexParameter (char parameterName[], dword iteration, char subParameter[], char buffer[], dword buffersize)`
- `diagRequest.GetComplexParameter (char parameterName[], dword iteration, char subParameter[], char buffer[], dword buffersize)`

### Description

Returns the symbolic value of a complex parameter. This is possible for all parameters.

### Parameters

- **obj**: Diagnostics object
- **parameterName**: Parameter qualifier
- **iteration**: Iteration (beginning with 0)
- **subParameter**: Sub parameter qualifier
- **buffer**: Output buffer
- **buffersize**: Buffer size

### Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

### Example

```plaintext
on diagResponse Door.FaultMemory_ReadAllIdentified
{
  dword DTC;
  char DTCasText[100];
  int i;

  if(diagIsPositiveResponse(this))
  {
    // Iterate over the list of DTCs and retrieve the numeric and symbolic value of each DTC
    for(i=0;i<DiagGetIterationCount(this,"ListOfDTC");i++)
    {
      DTC=DiagGetComplexParameter(this,"ListOfDTC",i,"DTC");
      DiagGetComplexParameter(this,"ListOfDTC", i, "DTC" , DTCasText, elCount(DTCasText));
      write("DTC %06X - %s",DTC, DTCasText);
    }
  }
  else
  {
    write("Negative response received.\nNegative response code: 0x%02X", (byte)DiagGetResponseCode(this));
  }
}
```
