[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetLastSecurityTaskResult.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetLastSecurityTaskResult

# diagGetLastSecurityTaskResult

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long diagGetLastSecurityTaskResult(char ecuQualifier[], long& resultCode);
```

## Description

Returns the result code of the last security task execution, specific to the configured security profile.

## Parameters

- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.
- **resultCode**: [out] code of the security task execution result.

## Return Values

- **0**: on success
- **otherwise**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```c
long error;
long result;
result = testWaitForDiagSecurityTaskCompleted("ECU",
           "Authenticate", "Authenticate", "Role=0x02", 1000);
if (result < 0)
{
    result = diagGetLastSecurityTaskResult("ECU", error);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)