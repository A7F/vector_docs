[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetConfiguredVariant.md)

**CAPL Functions** » **Diagnostics** » **diagGetConfiguredVariant**

# diagGetConfiguredVariant

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
long diagGetConfiguredVariant(char configuredVariantOut[], DWORD bufferLen); // form 1
long diagGetConfiguredVariant(char ecuQualifier[], char configuredVariantOut[], DWORD bufferLen); // form 2
```

## Description

Retrieves the qualifier of the variant that is configured for the current target. Retrieve the qualifier of the variant that is configured for the current or given target in the Diagnostics configuration dialog. It is possible to provide this qualifier to the automatic variant identification algorithm.

## Parameters

- **ecuQualifier**: ECU the identification algorithm should run for, not the currently selected one. If given, [diagSetTarget](CAPLfunctionDiagSetTarget.md) does not have to be called.
- **configuredVariantOut**: Buffer for the qualifier
- **bufferLen**: Length of the buffer

## Return Values

Length of qualifier written to buffer, may be truncated:

- **0**: No error, OK
- **<0**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)
- **-94**: Especially No target was selected

## Example

[Example](../CAPLfunctionsExampleAutomaticVariantIdentification.md)

[Automatic Variant Identification](../../../CANoeCANalyzer/Diagnostics/Test/DiagnosticsAutomaticVariantIdentification.md)

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)