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
