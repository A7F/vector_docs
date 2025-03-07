[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGenerateKeyResult.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » _Diag_GenerateKeyResult

# _Diag_GenerateKeyResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void _Diag_GenerateKeyResult(long result, BYTE computedKey[]);
```

## Description

Indicates the result of the security key computation which was started with [DiagStartGenerateKeyFromSeed](CAPLfunctionDiagStartGenerateKeyFromSeed.md).

## Parameters

- **result**: 
  - **0**: Success
  - **other**: Error code
- **computedKey**: Key as returned by the Seed & Key DLL, if any.

## Return Values

—

## Example

See: [DiagStartGenerateKeyFromSeed](CAPLfunctionDiagStartGenerateKeyFromSeed.md)

[Seed & Key DLL / Security Access](../../../CANoeCANalyzer/Diagnostics/Special/DiagSecurityDLLAccess.md) • [diagStartGenerateKeyFromSeed](CAPLfunctionDiagStartGenerateKeyFromSeed.md) • [diagGenerateKeyFromSeed](CAPLfunctionDiagGenerateKeyFromSeed.md) • [TestWaitForGenerateKeyFromSeed](../../Test/Functions/CAPLfunctionTestWaitForGenerateKeyFromSeed.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)