[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetObjectPath.md)

**CAPL Functions** » **Diagnostics** » **diagGetObjectPath**

# diagGetObjectPath

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long diagGetObjectPath (diagResponse obj, char buffer[], dword buffersize)
long diagGetObjectPath (diagRequest obj, char buffer[], dword buffersize)
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
long diagResponse::GetObjectPath (char buffer[], dword buffersize)
long diagRequest::GetObjectPath (char buffer[], dword buffersize)
```

## Description

Delivers the qualifier path of the object that must be specified upon generation.

## Parameters

- **obj**: Diagnostics object
- **buffer**: Input/output buffer
- **buffersize**: Buffer size

## Return Values

- Length of path written to buffer, may be truncated.
- [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```c
DumpReqParameterPaths( DiagRequest * req)
{
  DumpParameterPaths( req, 0);
}

DumpRespParameterPaths( DiagRequest * req)
{
  DumpParameterPaths( req, 1);
}

DumpParameterPaths( DiagRequest * req, long bDumpResponse)
{
  WORD i;
  char parameterPath[100];

  req.GetObjectPath( parameterPath, elcount( parameterPath));
  write( "Request is: %s", parameterPath);
  if( bDumpResponse)
    write( "Response parameters:");
  else
    write( "Request parameters:");

  i = 0;
  while( bDumpResponse && req.GetRespParameterPath( i, parameterPath, elcount( parameterPath)) > 0
    ||!bDumpResponse && req.GetParameterPath( i, parameterPath, elcount( parameterPath)) > 0)
  {
    write( "%2i %s", i, parameterPath);
    ++i;
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)