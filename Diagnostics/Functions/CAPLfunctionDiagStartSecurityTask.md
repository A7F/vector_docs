# diagStartSecurityTask, _diag_SecurityTaskFinished

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long diagStartSecurityTask(char ecuQualifier[], char taskId[], char jobQualifier[], char params[]);
void _diag_SecurityTaskFinished(char ecuQualifier[], char taskId[], long result); // result callback;
```

## Description

Starts a diagnostics generic security task. The result is indicated to the callback function `_diag_SecurityTaskFinished`.

## Parameters

- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.
- **taskId**: Identifier of the generic security task to be executed.
- **jobQualifier**: Diagnostic job to be used for the generic security task (parameter values). The job must be defined in the diagnostic description.
- **params**: Security task parameters - string with semi-colon separated key/value pairs.
- **result**: Result of the security task execution, see [error code](../CAPLfunctionsDiagnosticsErrorCode.md).

## Return Values

- **0**: on success
- **otherwise**: [Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
on key '1'
{
  long result = 0;
  result = diagStartSecurityTask("ECU", "Authenticate", "Authenticate", "Role=1");
}
void _diag_SecurityTaskFinished(char ecuQualifier[], char taskId[], long result)
{
  long error;

  write("Result of %s for %s = %d", taskId, ecuQualifier, result);

  if (result < 0)
  {
    result = diagGetLastSecurityTaskResult("ECU", error);
  }
}
```
