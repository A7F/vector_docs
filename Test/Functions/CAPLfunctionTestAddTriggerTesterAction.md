[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestAddTriggerTesterAction.md)

**CAPL Functions** » **Test Feature Set** » **TestAddTriggerTesterAction**

# TestAddTriggerTesterAction

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestAddTriggerTesterAction(long handle, Signal callbackTrigger);`
- `long TestAddTriggerTesterAction(long handle, sysVar callbackTrigger);`
- `long TestAddTriggerTesterAction(long handle, EnvVarName callbackTrigger);`
- `long TestAddTriggerTesterAction(long handle, long callbackCycle);`

## Description

Adds a trigger to a tester action previously created with [TestCreateTesterAction](CAPLfunctionTestCreateTesterAction.md). Every trigger triggers the call of the CAPL callback of its tester action cyclically or when the value of the signal, system variable, environment variable updates.

## Parameters

- **handle**: The handle of the tester action to add the trigger.
- **callbackTrigger**: The trigger when the condition has to be checked. It will always be checked when the value of the signal, system variable or environment variable updates.
- **callbackCycle**: Cycle time to check the condition.

## Return Values

- **> 0**: Handle of the trigger.
- **-1**: General error.

## Example

```plaintext
int CallbackTesterAction(int trigger)
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

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
