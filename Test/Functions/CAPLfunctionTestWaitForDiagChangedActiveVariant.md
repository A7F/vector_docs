[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForDiagChangedActiveVariant.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » testWaitForDiagChangedActiveVariant

# testWaitForDiagChangedActiveVariant

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long testWaitForDiagChangedActiveVariant(char variantQualifier[]); // form 1`
- `long testWaitForDiagChangedActiveVariant(char ecuQualifier[], char variantQualifier[]); // form 2`

## Description

Changes the active variant for the current target.

## Parameters

- **variantQualifier**: The variant to be used.
- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

- **≤ 0**: An error occurred, e.g. a wrong variant qualifier was used.
- **1**: The variant was successfully changed.

## Example

—

[Automatic Variant Identification](../../../CANoeCANalyzer/Diagnostics/Test/DiagnosticsAutomaticVariantIdentification.md) • [Diagnostic CAPL Functions: Variant Identification](../../Diagnostics/CAPLfunctionsDiagnosticsOverview.md#FunctionsVariantIdentification)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
