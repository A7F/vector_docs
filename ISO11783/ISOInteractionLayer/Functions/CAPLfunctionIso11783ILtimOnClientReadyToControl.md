[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimOnClientReadyToControl.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMOnClientReadyToControl

# Iso11783IL_TIMOnClientReadyToControl

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783IL_TIMOnClientReadyToControl(dword functionID, dword clientAddress)
```

## Description

This callback function is called if the TIM Client is ready to control a TIM function.

Within this callback you can call [Iso11783IL_TIMOperatorAcknowledge](CAPLfunctionIso11783ILtimOperatorAcknowledge.md) to acknowledge the request.

## Parameters

- **functionID**: Function ID of the TIM function.
  - **1-32 (1h-20h)**: Auxiliary Value 1 – 32, Supported Since TIM Version 1
  - **64 (40h)**: Front PTO, Supported Since TIM Version 1
  - **65 (41h)**: Rear PTO, Supported Since TIM Version 1
  - **66 (42h)**: Front hitch, Supported Since TIM Version 1
  - **67 (43h)**: Rear hitch, Supported Since TIM Version 1
  - **68 (44h)**: Vehicle speed, Supported Since TIM Version 1
  - **70 (46h)**: External guidance, Supported Since TIM Version 1
  - **71 (47h)**: Front top linkage, Supported Since TIM Version 2
  - **72 (48h)**: Rear top linkage, Supported Since TIM Version 2

- **clientAddress**: Address of TIM Client which is ready to control the function.

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
