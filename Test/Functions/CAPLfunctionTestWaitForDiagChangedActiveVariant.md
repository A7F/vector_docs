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
