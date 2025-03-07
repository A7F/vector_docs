[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestCreateTesterAction.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestCreateTesterAction

# TestCreateTesterAction

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestCreateTesterAction(char[] actionText, char[] heading, char[] callback);
long TestCreateTesterAction(char[] actionText, char[] heading, char[] resourceFile, char[] resourceCaption, char[] callback);
```

## Description

Creates a tester action. The condition is checked every time when the given trigger occurs. The check of the condition must be implemented in the given CAPL callback. The triggers have to be added with the [TestAddTriggerTesterAction](CAPLfunctionTestAddTriggerTesterAction.md) function.  
To execute the command call [TestValidateTesterAction](CAPLfunctionTestValidateTesterAction.md) with the handle of the tester action.

## Parameters

- **actionText**: Tester instruction of the popup window.
- **heading**: Heading of the popup window.
- **callback**: CAPL callback which is called every time to check the condition when the trigger occurs. The callback is also automatically called once before the popup opens and once before the popup closes after timeout occurs.

  Callback function must have the following signature:

  ```plaintext
  int mycallback(long trigger);
  ```

  The parameter **trigger** is the handle of the trigger which triggers the callback.

  The return value describes the result of the condition:

  - 0: condition is not fulfilled. Continue waiting
  - ≠0: condition is fulfilled. Stop waiting and end command

- **resourceFile**: The path of the resource image to show on the popup window.
- **resourceCaption**: The caption to show below the resource image.

## Return Values

- **> 0**: Handle of the tester action.
- **-1**: General error.

## Example

```plaintext
int CallbackTesterAction(long trigger)
{
  if (trigger == gTriggerCycle)
  {
    testStep("", "Triggered by cycle time");
  }
  else if (trigger == gTriggerSig)
  {
    testStep("", "Triggered by signal");
  }
  else if (trigger == gTriggerSV)
  {
    testStep("", "Triggered by system variable");
  }
  else if (trigger == gTriggerEV)
  {
    testStep("", "Triggered by environment variable");
  }
  else
  {
    testStep("", "Triggered before opening dialog or before closing dialog after timeout");
  }
  if(@sysVarEngineStarted == 1)
    return 1;

  return 0;
}

testcase TCTesterAction()
{
  long handle;

  handle = TestCreateTesterAction("This is the tester action text", "Tester action heading", "Resource.jpg", "Resource Caption", "CallbackTesterAction");

  gTriggerCycle = TestAddTriggerTesterAction(handle, 1000);
  gTriggerSig = TestAddTriggerTesterAction(handle, SigSigned16);
  gTriggerSV = TestAddTriggerTesterAction(handle, sysvar::sysInt);
  gTriggerEV = TestAddTriggerTesterAction(handle, EnvInt);

  TestValidateTesterAction(handle, 10000, 3);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)