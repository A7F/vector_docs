[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetIterationCount.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetIterationCount, diagGetRespIterationCount

# diagGetIterationCount, diagGetRespIterationCount

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `long diagGetIterationCount( diagRequest obj, char complexParamQualifier[]);`
- `long diagGetIterationCount( diagResponse obj, char complexParamQualifier[]);`
- `long diagGetRespIterationCount( diagRequest obj, char complexParamQualifier[]);`

## Method Syntax

- `long diagRequest::GetIterationCount(  char complexParamQualifier[]);`
- `long diagResponse::GetIterationCount( char complexParamQualifier[]);`
- `long diagRequest::GetRespIterationCount( char complexParamQualifier[]);`

## Description

Returns the number of sub-parameter iterations the complex parameter holds.

## Parameters

- **obj**: Diagnostic object.
- **complexParamQualifier**: Qualifier of the complex parameter that holds an iteration.

## Return Values

- **If > 0**: the number of iterations, otherwise an [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Example

```plaintext
testcase TC_ReadFaultMemory()
{
  diagRequest FaultMemory_ReadAllIdentified req;
  long count;
  req.SendRequest();
  TestWaitForDiagResponse( req, 1000);

  count = req.GetRespIterationCount( "ListOfDTC");
  while( count -- > 0)
    write( "DTC%d = %06x", count, req.GetComplexRespParameter( "ListOfDTC", count, "DTC"));
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)