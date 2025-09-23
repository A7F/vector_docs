[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForScopeEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitForScopeEvent

# testWaitForScopeEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long testWaitForScopeEvent(dword aTimeout);`
- `long testWaitForScopeEvent(enum ScopeEventType scopeEvent, dword aTimeout);`

## Description

Waits for the occurrence of Scope event. Should the event not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

## Parameters

- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.
- **scopeEvent** (optional): Type of the Scope event to be awaited. If not specified, the function will resume on any Scope event and the exact event type can be queried using [testGetWaitScopeEventData()](CAPLfunctionTestGetWaitScopeEventData.md).

  **Supported values:**

  - **scopeConnected**: Occurs when the **Connect Scope** action initiated with the [scopeConnect()](../../Scope/Functions/CAPLfunctionScopeConnect.md) CAPL call is successfully completed.
  - **scopeDisconnected**: Occurs when the **Disconnect Scope** action initiated with the [scopeDisconnect()](../../Scope/Functions/CAPLfunctionScopeDisconnect.md) CAPL call is successfully completed.
  - **scopeTriggerActivated**: Occurs when the Scope trigger activation initiated with the [scopeActivateTrigger()](../../Scope/Functions/CAPLfunctionScopeActivateTrigger.md) CAPL call is successfully completed.
  - **scopeTriggerDeactivated**: Occurs when the Scope trigger deactivation initiated with the [scopeDeactivateTrigger()](../../Scope/Functions/CAPLfunctionScopeDeactivateTrigger.md) CAPL call is successfully completed.
  - **scopeTriggered**: Occurs when the Scope triggering action initiated with the [scopeTriggerNow()](../../Scope/Functions/CAPLfunctionScopeTriggerNow.md) CAPL call is successfully completed.

## Return Values

- **1**: Resume due to event occurred
- **0**: Resume due to timeout
- **-1**: General error, for example, functionality is not available
- **-2**: Resume due to constraint violation

## Example

```c
long res;

res = scopeTriggerNow();
if (res != 1)
{
   testStepFail("Initialization","Call to scopeTriggerNow() failed. Return code =%d", res);
   return;
}

// wait till action done
if (testWaitForScopeEvent(eScopeTriggered, 8000) != 1)
{
   testStepFail("Initialization ","Scope event eScopeTriggered was not received");
   return;
}
testStep("Initialization","Scope hardware triggered successfully");
```

[Class ScopeEvent](../../Scope/Classes/CAPLfunctionsScopeEvent.md)
