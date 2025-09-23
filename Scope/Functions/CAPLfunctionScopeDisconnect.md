[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Scope/Functions/CAPLfunctionScopeDisconnect.md)

**CAPL Functions** » **Scope** » **scopeDisconnect**

# scopeDisconnect

**Valid for**: CANoe DE • CANoe:lite DE

**Note**  
**scopeDisconnect** must not be called within [on preStop](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) or [on stopMeasurement](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

## Function Syntax

```plaintext
long scopeDisconnect ();
```

## Description

Performs **Disconnect Scope** action for [Scope Window](../../../CANoeCANalyzer/SCOPE/Scope.md). This action is equivalent to disconnecting Scope via the GUI.

The completion of this action is reported with an internal event which can be awaited via TFS-function [testWaitForScopeEvent()](../../Test/Functions/CAPLfunctionTestWaitForScopeEvent.md) in CAPL programs for test modules.

## Parameters

—

## Return Values

- **2 (success)**: Scope is already disconnected. This might be a case when the disconnection has been done by a previous CAPL call or manually.
- **1 (success)**: Disconnection process started. On success an internal Scope event will be generated (see above). Failure can be recognized implicitly by not receiving the corresponding Scope event during certain timeout, e.g. during one second.
- **-1 (failure)**: Failure on disconnection request.

## Example

```plaintext
long res;

res = scopeDisconnect();
if (res <= 0 || res > 2)
{
   testStepFail("Initialization","Call to scopeDisconnect() failed. Return code =%d", res);
   return;
}
else if (res == 1)
{ // wait till action done
   if (testWaitForScopeEvent(eScopeDisconnected, 8000) != 1)
   {
      testStepFail("Initialization ","Scope event eScopeDisconnected was not received");
      return;
   }
}
testStep("Initialization","USB connection with the scope hardware is interrupted");
```
