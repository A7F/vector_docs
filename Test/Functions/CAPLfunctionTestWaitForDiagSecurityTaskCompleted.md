# TestWaitForDiagSecurityTaskCompleted

**Valid for**: CANoe DE • CANoe4SW DE

## Note

For more information on how this function is typically called and where to derive the corresponding parameters, check the dedicated OEM Security AddOn Manuals.

## Function Syntax

```plaintext
long testWaitForDiagSecurityTaskCompleted(char ecuQualifier[], char taskId[], char jobQualifier[], char params[], dword timeout);
```

## Description

Initiates the diagnostics generic security task and waits until this task has completed.

## Parameters

- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.
- **taskId**: Identifier of the generic security task to be executed.
- **jobQualifier**: Diagnostic job to be used for the generic security task (parameter values). The job must be defined in the diagnostic description.
- **params**: Security task parameters - string with semi-colon separated key/value pairs.
- **timeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **\< 0**: An internal error occurred, e.g. a protocol error or a faulty configuration of security access or diagnostic layer.
- **0**: The timeout was reached, i.e. the security task did not finish within the specified time.
- **1**: The security task finished successfully.

## Example

```plaintext
long error;
long result;

result = testWaitForDiagSecurityTaskCompleted("ECU",
        "Authenticate", "Authenticate", "Role=0x02", 1000);
if (result < 0)
{
    result = diagGetLastSecurityTaskResult("ECU", error);
}
```

[Test Feature Set CAPL Functions](../CAPLfunctionsTFSOverview.md)
