# diagStartAuth, diagStartAuthGeneric, _Diag_AuthResult

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `long diagStartAuth(char ecuQualifier[], char jobQualifier[]); // form 1`
- `long diagStartAuthGeneric(char ecuQualifier[], char genericString[]); // form 2`
- `void _Diag_AuthResult(long result); // form 3`

## Description

Starts the diagnostics authentication process. The result is indicated to the callback function `_Diag_AuthResult`.

## Parameters

- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.
- **genericString**: Generic parameters to select and configure the security source runtime implementation.
- **jobQualifier**: Diagnostic job to be executed. Should be defined in the diagnostic description.
- **result**: Result of the authentication process - see [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Return Values

0 on success otherwise [error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
on key 'a'
{
  result = diagStartAuth("Ecu", "Developer");
  write("Start 'diagStartAuth' for %s with result = %ld", gEcu, result);
}

void _Diag_AuthResult(long result)
{
  write("On '_Diag_AuthResult' for %s with result = %d", gEcu, result);
}
```
