# diagStartVariantIdentification

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagStartVariantIdentification(); // form 1`
- `long diagStartVariantIdentification(char ecuQualifier[]); // form 2`

## Description

Start the automatic variant identification algorithm for the given target, or the currently selected one if none is given. The algorithm will communicate via the built-in diagnostic channel, i.e. the CAPL callback functions are not used for the identification.

A tester module may wait for the completion of the algorithm with [testWaitForDiagVariantIdentificationCompleted](../../Test/Functions/CAPLfunctionTestWaitForDiagVariantIdentificationCompleted.md), or query the status of the identification with [diagGetIdentifiedVariant](CAPLfunctionDiagGetIdentifiedVariant.md).

## Parameters

- **ecuQualifier**: ECU the identification algorithm should run for, not the currently selected one. If given, [diagSetTarget](CAPLfunctionDiagSetTarget.md) does not have to be called.

## Return Values

- **0**: No error, algorithm was started
- **< 0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md), especially:
  - **-98**: No communication channel could be found for the target
  - **-97**: Automatic variant identification is not defined in the diagnostic description
  - **-91**: The variant identification algorithm is already running

## Example

Unlock ECU after pressing `<u>`.

[Example](../CAPLfunctionsExampleAutomaticVariantIdentification.md)

[Automatic Variant Identification](../../../CANoeCANalyzer/Diagnostics/Test/DiagnosticsAutomaticVariantIdentification.md)
