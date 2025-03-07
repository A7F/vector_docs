[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetIdentifiedVariant.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetIdentifiedVariant

# diagGetIdentifiedVariant

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagGetIdentifiedVariant(char identifiedVariantOut[], dword bufferLen); // form 1`
- `long diagGetIdentifiedVariant(char ecuQualifier[], char identifiedVariantOut[], dword bufferLen); // form 2`

## Description

Retrieve the qualifier of the variant that has been identified by the last successful run of the automatic variant identification algorithm for given target, or the current target if no target is given. The function can also be used to determine whether the algorithm has finished.

## Parameters

- **ecuQualifier**: ECU the identification algorithm should run for, not the currently selected one. If given, [diagSetTarget](CAPLfunctionDiagSetTarget.md) does not have to be called.
- **identifiedVariantOut**: Buffer for the qualifier
- **bufferLen**: Length of the buffer

## Return Values

- **≥ 0**: Number of characters written into the buffer
- **< 0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)
  - **-99**: The algorithm is still running, try again later
  - **-98**: No variant was identified, e.g. the algorithm was not started or failed

## Example

[Example](../CAPLfunctionsExampleAutomaticVariantIdentification.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)