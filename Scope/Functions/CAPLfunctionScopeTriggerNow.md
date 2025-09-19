[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Scope/Functions/CAPLfunctionScopeTriggerNow.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../CAPLfunctionsScopeOverview.md) » scopeTriggerNow

# scopeTriggerNow

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long scopeTriggerNow();
```

## Description

Performs **Trigger Now** action for [Scope Window](../../../CANoeCANalyzer/SCOPE/Scope.md). This action is equivalent to immediate triggering via the GUI.

The completion of this action is reported with an internal event which can be awaited via TFS-function [testWaitForScopeEvent()](../../Test/Functions/CAPLfunctionTestWaitForScopeEvent.md) in CAPL programs for test modules.

## Parameters

—

## Return Values

- **1 (success)**: Trigger signal has been generated. On trigger completion an internal Scope event will be generated (see above). Failure can be recognized implicitly by not receiving the corresponding Scope event during certain timeout, e.g. during one second.
- **-1 (failure)**: The Scope connection is not established.
- **-2 (failure)**: The data fetching is not completed yet.
- **-3 (failure)**: Memory overflow.

## Example

```plaintext
long res;

res = scopeTriggerNow();
if (res != 1)
{
   testStepFail("Initialization","Call to scopeTriggerNow() failed. Return code =%d", res);
   return;
}

// wait till action done
if (testWaitForScopeEvent(eScopeTriggered, 50000) != 1)
{
   testStepFail("Initialization ","Scope event eScopeTriggered was not received");
   return;
}
testStep("Initialization","Scope hardware triggered successfully");
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
