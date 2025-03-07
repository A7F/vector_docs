[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForDiagVariantIdentificationCompleted.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForDiagVariantIdentificationCompleted, TestWaitForDiagEcuVariantIdentificationCompleted

# TestWaitForDiagVariantIdentificationCompleted, TestWaitForDiagEcuVariantIdentificationCompleted

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForDiagVariantIdentificationCompleted(); // form 1`
- `long TestWaitForDiagVariantIdentificationCompleted( char expectedVariant[]); // form 2`
- `long TestWaitForDiagVariantIdentificationCompleted( char ecuQualifier[], char expectedVariant[]); // form 3`
- `long TestWaitForDiagEcuVariantIdentificationCompleted( char ecuQualifier[]); // form 4`

## Description

Waits for the completion of the automatic variant identification algorithm. If the qualifier of an expected variant is given, an error is returned if a different variant is identified.

## Parameters

- **expectedVariant**: Qualifier of the variant that should be identified.
- **ecuQualifier**: Wait for the completion of the variant identification for this diagnostic ECU. No call to DiagSetTarget is necessary if this parameter is given.

## Return Values

- **1**: Identification algorithm finished successfully.
- **0**: Timeout (10 seconds).
- **< 0**: [Error code](../../Diagnostics/CAPLfunctionsDiagnosticsErrorCode.md), especially:
  - **-100**: Variant identification not running - DiagStartVariantIdentification must be called!
  - **-98**: No variant was identified, i.e. the algorithm failed
  - **-90**: TestWaitFor... functions are only possible in tester modules
  - **-83**: The identified variant was not the expected one

## Example

[Example](../../Diagnostics/CAPLfunctionsExampleAutomaticVariantIdentification.md)

[Automatic Variant Identification](../../../CANoeCANalyzer/Diagnostics/Test/DiagnosticsAutomaticVariantIdentification.md) • [Diagnostic CAPL Functions: Variant Identification](../../Diagnostics/CAPLfunctionsDiagnosticsOverview.md#FunctionsVariantIdentification)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)