[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimOnFunctionValueChanged.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMOnFunctionValueChanged

# Iso11783IL_TIMOnFunctionValueChanged

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783IL_TIMOnFunctionValueChanged(dword functionID, dword newRawValue)
```

## Description

This callback function is called if the value of a function has been changed due to a function request message. It is not called when a function request command failed (e.g. because function is not assigned or value is out of range).

## Parameters

- **functionID**: Function ID of the TIM function.

  - **Function ID**: 1-32 (1h-20h)
    - **Description**: Auxiliary Value 1 – 32
    - **Supported Since TIM Version**: 1

  - **Function ID**: 64 (40h)
    - **Description**: Front PTO
    - **Supported Since TIM Version**: 1

  - **Function ID**: 65 (41h)
    - **Description**: Rear PTO
    - **Supported Since TIM Version**: 1

  - **Function ID**: 66 (42h)
    - **Description**: Front hitch
    - **Supported Since TIM Version**: 1

  - **Function ID**: 67 (43h)
    - **Description**: Rear hitch
    - **Supported Since TIM Version**: 1

  - **Function ID**: 68 (44h)
    - **Description**: Vehicle speed
    - **Supported Since TIM Version**: 1

  - **Function ID**: 70 (46h)
    - **Description**: External guidance
    - **Supported Since TIM Version**: 1

  - **Function ID**: 71 (47h)
    - **Description**: Front top linkage
    - **Supported Since TIM Version**: 2

  - **Function ID**: 72 (48h)
    - **Description**: Rear top linkage
    - **Supported Since TIM Version**: 2

- **newRawValue**: New raw value of the function.

## Return Values

—

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
