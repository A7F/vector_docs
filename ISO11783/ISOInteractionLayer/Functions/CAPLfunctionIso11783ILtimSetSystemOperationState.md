[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetSystemOperationState.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMSetSystemOperationState

# Iso11783IL_TIMSetSystemOperationState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMSetSystemOperationState(dword state)` // form 1
- `long Iso11783IL_TIMSetSystemOperationState(dbNode server, dword state)` // form 2

## Description

Sets the current system operation state of a TIM Server. This state is transmitted in the **TIM_ServerStatus_Msg** message. But it does not influence the functionality of the TIM server.

## Parameters

- **state**: New system operation state.
  - **0**: Requirements for TIM operation are not fulfilled
  - **1**: Requirements for normal operation are fulfilled
  - **2**: Requirements for standstill operation are fulfilled
  - **3**: Requirements for stationary operation are fulfilled
  - **4-13**: Reserved
  - **14**: Error
  - **15**: Not available

- **server**: TIM server simulation node to apply the function.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
