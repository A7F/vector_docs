[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Scope/Functions/CAPLfunctionScopeDeactivateTrigger.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../CAPLfunctionsScopeOverview.md) » scopeDeactivateTrigger

# scopeDeactivateTrigger

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long scopeDeactivateTrigger();
```

## Description

Performs **Deactivate Trigger** action for [Scope Window](../../../CANoeCANalyzer/SCOPE/Scope.md). This action is equivalent to deactivating the trigger via the GUI.

The completion of this action is reported with an internal event which can be awaited via TFS-function [testWaitForScopeEvent()](../../Test/Functions/CAPLfunctionTestWaitForScopeEvent.md) in CAPL programs for test modules.

## Parameters

—

## Return Values

- **2 (success)**: Trigger is already inactive. This might be a case when the trigger has been deactivated by a previous CAPL call or manually.
- **1 (success)**: Trigger deactivation process started. On success an internal Scope event will be generated (see above). Failure can be recognized implicitly by not receiving the corresponding Scope event during certain time-out, e.g. during one second.
- **-1 (failure)**: Failure on stop capture request.

## Example

```plaintext
long res;

res = scopeDeactivateTrigger();
if (res <= 0 || res > 2)
{
   testStepFail("Initialization","Call to scopeDeactivateTrigger() failed. Return code =%d", res);
   return;
}
else if (res == 1)
{ // wait till action done
   if (testWaitForScopeEvent(eScopeTriggerDeactivated, 8000) != 1)
   {
      testStepFail("Initialization ","Scope event eScopeTriggerDeactivated was not received");
      return;
   }
}
testStep("Initialization","Scope trigger deactivation succeeded");
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
