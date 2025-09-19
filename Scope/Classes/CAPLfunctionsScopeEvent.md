[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Scope/Classes/CAPLfunctionsScopeEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../CAPLfunctionsScopeOverview.md) » Class: ScopeEvent

# Class: ScopeEvent

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

## Methods

—

## Attributes

- **Type**: Type of scope event.  
  **Type**: enum ScopeEventType  
  **Access Limitations**: Read-only

- **DataID**: Data identifier of the captured data created after request to trigger on Scope hardware completed.  
  **Type**: int  
  **Access Limitations**: Read-only

- **Time**: Time stamp of the captured data created after request to trigger on Scope hardware completed.  
  **Type**: int64  
  **Access Limitations**: Read-only

- **TriggerInformation**: Hold the information of a trigger event, if the type of the scope event is scopeTriggered.  
  **Type**: [scopeTriggerInformation](CAPLfunctionsScopeTriggerInformation.md)  
  **Access Limitations**: Read-only

## enum ScopeEventType

- **scopeConnected**: Occurs when the **Connect Scope** action initiated with the [scopeConnect()](../Functions/CAPLfunctionScopeConnect.md) CAPL call is successfully completed.

- **scopeDisconnected**: Occurs when the **Disconnect Scope** action initiated with the [scopeDisconnect()](../Functions/CAPLfunctionScopeDisconnect.md) CAPL call is successfully completed.

- **scopeTriggerActivated**: Occurs when the Scope trigger activation initiated with the [scopeActivateTrigger()](../Functions/CAPLfunctionScopeActivateTrigger.md) CAPL call is successfully completed.

- **scopeTriggerDeactivated**: Occurs when the Scope trigger deactivation initiated with the [scopeDeactivateTrigger()](../Functions/CAPLfunctionScopeDeactivateTrigger.md) CAPL call is successfully completed.

- **scopeTriggered**: Occurs when the Scope triggering action initiated with the [scopeTriggerNow()](../Functions/CAPLfunctionScopeTriggerNow.md) CAPL call is successfully completed.

[testGetWaitScopeEventData](../../Test/Functions/CAPLfunctionTestGetWaitScopeEventData.md) • [testWaitForScopeEvent](../../Test/Functions/CAPLfunctionTestWaitForScopeEvent.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
