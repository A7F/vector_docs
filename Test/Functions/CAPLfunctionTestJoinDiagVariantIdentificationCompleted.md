[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinDiagVariantIdentificationCompleted.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinDiagVariantIdentificationCompleted

# TestJoinDiagVariantIdentificationCompleted

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

`long testJoinDiagVariantIdentificationCompleted(char ecuQualifier[]);`

## Description

Adds an event to the set of joined events that will fire when the variant identification started for the given ECU is completed.

## Parameters

- **ecuQualifier**: The event will fire on the completion of the variant identification for this ECU.

## Return Values

Number of conditions in stock:

- **-100**: Input parameter error, i.e. the variant identification is not running for this ECU.
- **-3**: Error while adding the specified event to the set of joined events.
- **-1**: General error, for example, functionality is not available.
- **> 0**: Number of the newly joined event.

[Error code](../../Diagnostics/CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
testcase TC_ParallelIdentification()
{
  // Perform variant identification for 3 ECUs in parallel
  diagStartVariantIdentification("ECU1");
  testJoinDiagVariantIdentificationCompleted("ECU1");
  diagStartVariantIdentification("ECU2");
  testJoinDiagVariantIdentificationCompleted("ECU2");
  diagStartVariantIdentification("ECU3");
  testJoinDiagVariantIdentificationCompleted("ECU3");

  if( 0 < TestWaitForAllJoinedEvents(5000))
    TestStepPass( "All variant identification tasks completed in time.");
  else
    TestStepFail( "Not all variant identification tasks completed in time!");

  {
    char identifiedVariant[100];
    diagGetIdentifiedVariant( "ECU1", identifiedVariant, elcount(identifiedVariant));
    if( 0 == strncmp( identifiedVariant, "Beta", 5))
      TestStepFail( "Should not run this test with beta version!");
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
