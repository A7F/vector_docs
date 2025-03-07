[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Scope/Functions/CAPLfunctionScopeActivateTrigger.md)

**CAPL Functions** » [Scope](../CAPLfunctionsScopeOverview.md) » scopeActivateTrigger

# scopeActivateTrigger

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long scopeActivateTrigger ();
```

## Description

Performs **Activate Trigger** action for [Scope window](../../../CANoeCANalyzer/SCOPE/Scope.md). This action is equivalent to activating the trigger via the GUI.

The completion of this action is reported with an internal event which can be awaited via TFS-function [testWaitForScopeEvent()](../../Test/Functions/CAPLfunctionTestWaitForScopeEvent.md) in CAPL programs for test modules.

## Parameters

—

## Return Values

- **2 (success)**: Trigger is already active. This might be a case when the trigger has been activated by a previous CAPL call or manually.
- **1 (success)**: Trigger activation process started. On success an internal Scope event will be generated (see above). Failure can be recognized implicitly by not receiving the corresponding Scope event during certain timeout, e.g. during one second.
- **-1 (failure)**: There is no valid Scope hardware device configured.
- **-2 (failure)**: The Scope connection is not established.

## Example

```plaintext
long res;

res = scopeActivateTrigger();
if (res <= 0 || res > 2)
{
   testStepFail("Initialization","Call to scopeActivateTrigger() failed. Return code =%d", res);
   return;
}
else if (res == 1)
{ // wait till action done
   if (testWaitForScopeEvent(eScopeTriggerActivated, 8000) != 1)
   {
      testStepFail("Initialization ","Scope event eScopeTriggerActivated was not received");
      return;
   }
}
testStep("Initialization","Scope trigger activation succeeded");
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)