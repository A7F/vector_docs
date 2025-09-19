[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Scope/Classes/CAPLfunctionsScopeTriggerInformation.md)

**CAPL Functions** » **Scope** » **Class: scopeTriggerInformation**

# Class: scopeTriggerInformation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Methods

—

## Attributes

- **Keyword**: triggerName
  - **Description**: The name of the trigger.
  - **Type**: char[256]
  - **Access Limitations**: Read-only

- **Keyword**: triggerType
  - **Description**: The type of the trigger.
    - **Values**:
      - eUnknownTrigger = -1
      - eManualTrigger = 0
      - eFrameTrigger = 1
      - eIOTrigger = 2
  - **Type**: long
  - **Access Limitations**: Read-only

- **Keyword**: triggerTime
  - **Description**: Time stamp of the event was triggered in case of **FrameTrigger**.
  - **Type**: int64
  - **Access Limitations**: Read-only

- **Keyword**: triggerRequestTime
  - **Description**: Time stamp the trigger was request by CANoe in case of **FrameTrigger** and **ManualTrigger**.
  - **Type**: int64
  - **Access Limitations**: Read-only

- **Keyword**: triggerScopeTime
  - **Description**: Time stamp the scope has triggered in case of **FrameTrigger** and **IOTrigger**.
  - **Type**: int64
  - **Access Limitations**: Read-only

[testGetWaitScopeEventData](../../Test/Functions/CAPLfunctionTestGetWaitScopeEventData.md) • [testWaitForScopeEvent](../../Test/Functions/CAPLfunctionTestWaitForScopeEvent.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
