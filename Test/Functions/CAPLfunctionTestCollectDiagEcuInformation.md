# TestCollectDiagEcuInformation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `TestCollectDiagEcuInformation(char class[]); // form 1`
- `TestCollectDiagEcuInformation(char ecuQualifier[], char class[]); // from 2`

## Description

Sends diagnostic requests to the currently selected diagnostic target or the given ECU and writes the responses to the report file. It considers all requests below a diagnostic class that have constant parameters only.

## Parameters

- **class**: The qualifier of the diagnostic class.
- **ecuQualifier**: The qualifier of the ECU.

## Return Values

[Error code](../../Diagnostics/CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```c
testcase IdentifyAllEcus()
{
  char ecuQual[200];
  long i;
  i = diagGetTargetCount();
  while( i-- > 0)
  {
    long class;
    long status;
    if( 0 >= diagGetTargetQualifier( i, ecuQual, elcount( ecuQual)))
    {
      TestStepFail( "", "Cannot retrieve qualifier of ECU target %d", i);
      continue;
    }
    write( "Collecting information from target %s", ecuQual);
    status = TestCollectDiagEcuInformation( ecuQual, "Identification");
    if( status == 0)
      TestStepPass( "ECU information collected successfully");
    else
      TestStepFail( "", "Error %d collecting information from ECU %s", status, ecuQual);
  }
}
```

[Test Feature Set CAPL Functions](../CAPLfunctionsTFSOverview.md)
