[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetPrimitiveSize.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetPrimitiveSize

# diagGetPrimitiveSize

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long DiagGetPrimitiveSize( diagRequest request);
long DiagGetPrimitiveSize( diagResponse response);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
diagRequest::GetPrimitiveSize();
diagResponse::GetPrimitiveSize();
```

## Description

Returns the byte length of the object.

## Parameters

- **request**: Request
- **response**: Response

## Return Values

- **> 0**: Number of bytes.
- **< 0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

The following example shows how to retrieve parameter values via symbolic access while using an universal "on diagRequest" handler ("*").

```plaintext
// e.g. used in a Tester module
on diagResponse *
{
  byte data[4096];
  long size;
  double param_value1=0xFF;
  double param_value2=0xFF;
  diagResponse * resp; // declare response with no concrete interpretation

  size=this.GetPrimitiveSize(); // get length of response
  this.GetPrimitiveData(data, elcount(data)); // copy actual response from "on diagResponse *" into data array

  switch(data[0]) 
  {
    case 0x50: // UDS: DiagnosticSessionControl_Process positive Response
      diagInitialize(resp, "DiagnosticSessionControl_Process");
      resp.Resize(size); // make sure there is room for the received bytes
      resp.SetPrimitiveData(data, size); // initialize resp with actual response from data array
      param_value1=diagGetParameter(resp, "diagnosticSessionType");
      param_value2=diagGetParameter(resp, "sessionParameterRecord");
      break;
    case 0x51: // UDS: EcuReset_Process positive Response
      diagInitialize(resp, "EcuReset_Process");
      resp.Resize(size); // make sure there is room for the received bytes
      resp.SetPrimitiveData(data, size); // initialize resp with actual response from data array
      param_value1=diagGetParameter(resp, "resetType");
      param_value2=diagGetParameter(resp, "powerDownTime");
      break;
    default:
      break;
  }
  write("Tester: Value of parameter according to chosen interpretation: 0x%x 0x%x %3.0lf %3.0lf",data[0], data[1], param_value1, param_value2);
}
```

[diagGetRespPrimitiveSize](CAPLfunctionDiagGetRespPrimitiveSize.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)