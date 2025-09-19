[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestValidateTesterAction.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestValidateTesterAction

# TestValidateTesterAction

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestValidateTesterAction(char[] actionText, char[] heading, char[] callback, DWORD timeout, long resultOnAbort, Signal callbackTrigger); //form 1`
- `long TestValidateTesterAction(char[] actionText, char[] heading, char[] callback, DWORD timeout, long resultOnAbort, sysVar callbackTrigger); // form 2`
- `long TestValidateTesterAction(char[] actionText, char[] heading, char[] callback, DWORD timeout, long resultOnAbort, EnvVarName callbackTrigger); // form 3`
- `long TestValidateTesterAction(char actionText[], char heading[], char[] callback, DWORD timeout, long resultOnAbort, DWORD callbackCycle); // form 4`
- `long TestValidateTesterAction(long handle, DWORD timeout, long resultOnAbort); // form 5`

## Description

Creates a popup window with the given tester instruction. The window closes automatically when the needed condition is fulfilled or after user cancel. The condition is checked every time when the given trigger occurs. The check of the condition must be implemented in the given CAPL callback.

The window contains a field for entering a comment which is automatically adopted into the test report. The result of the command is reported.

The function is not allowed in [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md). Errors are reported as **error in test system** or **fail** in case of 2-valued verdict concept.

Form 5 is used with the functions [TestCreateTesterAction](CAPLfunctionTestCreateTesterAction.md) and [TestAddTriggerTesterAction](CAPLfunctionTestAddTriggerTesterAction.md) to create complex tester actions with multiple triggers.

## Parameters

- **actionText**: Tester instruction of the popup window.
- **heading**: Heading of the popup window.
- **callback**: CAPL callback which is called every time to check the condition when the trigger occurs. The callback is also automatically called once before the popup opens and once before the popup closes after timeout occurs.

  Callback function must have the following signature:

  ```c
  int mycallback();
  ```

  The return value describes the result of the condition:
  - 0: condition is not fulfilled. Continue waiting
  - ≠0: condition is fulfilled. Stop waiting and end command

- **timeout**: Maximum time (in milliseconds) to wait for a fulfilled condition. If timeout occurs command ends with **resultOnAbort**.
- **resultOnAbort**: Result to report if timeout occurs or after user cancel.

  Possible values:
  - 0: pass
  - 1: fail
  - 3: inconclusive
  - 4: error in test system

- **callbackTrigger**: The trigger when the condition has to be checked. It will always be checked when the value of the signal, system variable or environment variable updates.
- **callbackCycle**: Cycle time to check the condition.
- **handle**: The handle of the created tester action.

## Return Values

- **0**: Timeout occurs.
- **1**: Condition was fulfilled.
- **2**: User cancel
- **-1**: Error

## Example

```c
int CallbackSignal()
{
  if(@sysVarEngineStarted == 1)
    return 1;

  return 0;
}

testcase TCTesterAction()
{
  TestValidateTesterAction("This is the tester action text", "Tester action heading", "CallbackSignal", 10000, 3, SigSigned16);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
