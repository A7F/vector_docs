[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestValidateDiagAuthGeneric.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » testValidateDiagAuthGeneric, testValidateDiagAuth

# testValidateDiagAuthGeneric, testValidateDiagAuth

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long testValidateDiagAuthGeneric(
  const char ecuQualifier, const char genericString); // form 1
```

```
long testValidateDiagAuth(
  const char ecuQualifier, const char jobQualifier); // form 2
```

## Description

Initiates the diagnostics authentication process and waits until this process has (generic) completed. The test step is then evaluated as passed or failed, depending on the result, and documented in the report.

## Parameters

- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.
- **genericString**: Generic parameters to select and configure the security source runtime implementation.
- **jobQualifier**: Diagnostic job to be executed. Should be defined in the diagnostic description.

## Return Values

On success 0, otherwise [error code](../../Diagnostics/CAPLfunctionsDiagnosticsErrorCode.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
