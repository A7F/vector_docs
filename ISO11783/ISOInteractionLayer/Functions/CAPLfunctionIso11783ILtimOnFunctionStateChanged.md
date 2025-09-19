[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimOnFunctionStateChanged.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_TIMOnFunctionStateChanged

# Iso11783IL_TIMOnFunctionStateChanged

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void Iso11783IL_TIMOnFunctionStateChanged(dword functionID, dword newState)
```

## Description

This callback function is called if the state of a TIM function has been changed. If this callback function is used by a TIM client the function is only called if the TIM function is assigned by the client.

You can also use the function [Iso11783IL_TIMConnectSysVarToFunctionState](CAPLfunctionIso11783ILtimConnectSysVarToFunctionState.md) if you are interested in the state of a function.

## Parameters

- **functionID**: Function ID of the TIM function.
  - **Function ID**: 1-32 (1h-20h), **Description**: Auxiliary Value 1 – 32, **Supported Since TIM Version**: 1
  - **Function ID**: 64 (40h), **Description**: Front PTO, **Supported Since TIM Version**: 1
  - **Function ID**: 65 (41h), **Description**: Rear PTO, **Supported Since TIM Version**: 1
  - **Function ID**: 66 (42h), **Description**: Front hitch, **Supported Since TIM Version**: 1
  - **Function ID**: 67 (43h), **Description**: Rear hitch, **Supported Since TIM Version**: 1
  - **Function ID**: 68 (44h), **Description**: Vehicle speed, **Supported Since TIM Version**: 1
  - **Function ID**: 70 (46h), **Description**: External guidance, **Supported Since TIM Version**: 1
  - **Function ID**: 71 (47h), **Description**: Front top linkage, **Supported Since TIM Version**: 2
  - **Function ID**: 72 (48h), **Description**: Rear top linkage, **Supported Since TIM Version**: 2

- **newState**: New state of the TIM function.
  - **State**: 0, **Description**: Automation unavailable
  - **State**: 1, **Description**: Automation not ready
  - **State**: 2, **Description**: Automation ready to enable
  - **State**: 3, **Description**: Automation enabled
  - **State**: 4, **Description**: Automation pending
  - **State**: 5, **Description**: Active, not limited
  - **State**: 6, **Description**: Active, limited high
  - **State**: 7, **Description**: Active, limited low
  - **State**: 14, **Description**: Non-recoverable fault
  - **State**: 15, **Description**: Not available (parameter not supported or not configured for TIM)

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
