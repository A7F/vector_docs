[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimGetFunctionState.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_TIMGetFunctionState

# Iso11783IL_TIMGetFunctionState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMGetFunctionState(dword functionID, dword& currentState); // form 1`
- `long Iso11783IL_TIMGetFunctionState(dword functionID, dword& currentState, dword& counterpartAddress); // form 2`
- `long Iso11783IL_TIMGetFunctionState(dbNode participant, dword functionID, dword& currentState); // form 3`
- `long Iso11783IL_TIMGetFunctionState(dbNode participant, dword functionID, dword& currentState, dword& counterpartAddress); // form 4`

## Description

Returns the current state of a TIM function.

If this function is called for a TIM client, the function returns state **0** (Automation unavailable) if the TIM function is not assigned by the client.

## Parameters

- **functionID**: Function ID of the TIM function.

- **currentState**: Returns the current state of the TIM function.
  - **0**: Automation unavailable
  - **1**: Automation not ready
  - **2**: Automation ready to enable
  - **3**: Automation enabled
  - **4**: Automation pending
  - **5**: Active, not limited
  - **6**: Active, limited high
  - **7**: Active, limited low
  - **14**: Non-recoverable fault
  - **15**: Not available (parameter not supported or not configured for TIM)

- **counterpartAddress**: Returns the address of the TIM counterpart.

- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

[Iso11783IL_TIMOnFunctionStateChanged](CAPLfunctionIso11783ILtimOnFunctionStateChanged.md)
