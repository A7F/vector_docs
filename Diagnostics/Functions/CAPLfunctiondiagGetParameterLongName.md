[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctiondiagGetParameterLongName.md)

**CAPL Functions** » **Diagnostics** » **diagGetParameterLongName, diagGetRespParameterLongName**

# diagGetParameterLongName, diagGetRespParameterLongName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long diagGetParameterLongName (diagResponse obj, dword paramNo, char buffer[], dword buffersize);
long diagGetParameterLongName (diagRequest obj, dword paramNo, char buffer[], dword buffersize);
long diagGetRespParameterLongName (diagRequest obj, dword paramNo, char buffer[], dword buffersize);
long diagGetParameterLongName (diagResponse obj, char paramPath[], char buffer[], dword buffersize);
long diagGetParameterLongName (diagRequest obj, char paramPath[], char buffer[], dword buffersize);
long diagGetRespParameterLongName (diagRequest obj, char paramPath[], char buffer[], dword buffersize);
```

## Method Syntax

```
long diagResponse::GetParameterLongName (dword paramNo, char buffer[], dword buffersize);
long diagRequest::GetParameterLongName (dword paramNo, char buffer[], dword buffersize);
long diagRequest::GetRespParameterLongName (dword paramNo, char buffer[], dword buffersize);
long diagResponse::GetParameterLongName (char paramPath[], char buffer[], dword buffersize);
long diagRequest::GetParameterLongName (char paramPath[], char buffer[], dword buffersize);
long diagRequest::GetRespParameterLongName (char paramPath[], char buffer[], dword buffersize);
```

## Description

Copies the **long name** of a diagnostic parameter into the buffer, honoring the character encoding configured in the diagnostic description. The text is converted into the encoding used in the CAPL program.

There are two ways to identify the parameter:

- with index: like [DiagGetParameterName](CAPLfunctionDiagGetParameterName.md), the index will also count structural parameter that cannot have a symbolic value, but of course have a name.
- with parameter path: the path of the parameter, either inserted using the symbol explorer, or returned by the function [DiagGetParameterPath](CAPLfunctionDiagGetParameterPath.md). That function only counts leaf parameters since those can have a symbolic representation.

## Parameters

- **obj**: Diagnostic object.
- **paramNo**: Which parameter in the object, beginning with **0**.
- **paramPath**: Parameter in the object, identified by its qualifier (path).
- **buffer**: Output buffer. Character encoding of the CAPL file will be honored.
- **bufferSize**: Buffer size.

## Return Values

- Length of path written to buffer, may be truncated.
- [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```cpp
// Write the parameter paths, names and symbolic values of a response object to the Write Window
DumpResponseParameterPaths( DiagResponse * resp)
{
  WORD i;
  char path[100];

  resp.GetObjectPath( path, elcount( path));
  write( "Object: %s", path);

  i = 0;
  while( resp.GetParameterPath( i, path, elcount( path)) > 0)
  {
    char parameterSymbol[200];
    char name[200];
    resp.GetParameter( path, parameterSymbol, elcount( parameterSymbol));
    DiagGetParameterLongName( resp, path, name, elcount(name));
    write( "%2i %-50s %-20s = %s", i, path, name, parameterSymbol);
    ++i;
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)