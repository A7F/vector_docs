[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForDiagSetIdentifiedVariant.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » testWaitForDiagSetIdentifiedVariant

# testWaitForDiagSetIdentifiedVariant

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long testWaitForDiagSetIdentifiedVariant(); // form 1`
- `long TestWaitForDiagSetIdentifiedVariant(char ecuQualifier[]); // form 2`

## Description

Performs a variant identification and activates the found variant.

## Parameters

- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

- **≤ 0**: An error occurred, e.g. a wrong variant Qualifier was used or a communication error occurred.
- **1**: The variant was successfully changed.

## Example

—

[Automatic Variant Identification](../../../CANoeCANalyzer/Diagnostics/Test/DiagnosticsAutomaticVariantIdentification.md) • [Diagnostic CAPL Functions: Variant Identification](../../Diagnostics/CAPLfunctionsDiagnosticsOverview.md#FunctionsVariantIdentification)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
