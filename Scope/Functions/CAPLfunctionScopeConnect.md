[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Scope/Functions/CAPLfunctionScopeConnect.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../CAPLfunctionsScopeOverview.md) » scopeConnect

# scopeConnect

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long scopeConnect();
```

## Description

Performs **Connect Scope** action for [Scope Window](../../../CANoeCANalyzer/SCOPE/Scope.md). This action is equivalent to connecting Scope via the GUI. The Scope Window will be opened automatically if not yet opened.

The completion of this action is reported with an internal event which can be awaited via TFS-function [testWaitForScopeEvent()](../../Test/Functions/CAPLfunctionTestWaitForScopeEvent.md) in CAPL programs for test modules.

## Parameters

—

## Return Values

- **2 (success)**: Connection is already established. This might be a case when connection has been established by a previous CAPL call or manually.
- **1 (success)**: Connection process started. On success an internal Scope event will be generated (see above). Failure can be recognized implicitly by not receiving the corresponding Scope event during certain timeout, e.g. during one second.
- **-1 (failure)**: Failure on connection request.

## Example

```plaintext
long res;

res = scopeConnect();
if (res < 0 || res > 2)
{
   testStepFail("Initialization"," Call to scopeConnect() failed. Return code =%d", res);
   return;
}
else if (res == 1)
{ // wait till action done
   if (testWaitForScopeEvent(eScopeConnected, 8000) != 1)
   {
      testStepFail("Initialization ","Scope event eScopeConnected was not received");
      return;
   }
}
testStep("Initialization","USB connection with the scope hardware is established");
```
