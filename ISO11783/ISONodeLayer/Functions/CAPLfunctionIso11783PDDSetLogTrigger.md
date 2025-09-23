# Iso11783PDDSetLogTrigger

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long Iso11783PDDSetLogTrigger( dword ecuHandle, dword command, ulong ddi, ulong elNum, ulong value );
```

## Description

A measurement command can be executed with this function. It can be used in the callback function [Iso11783PDDOnDefaultLogRequest](CAPLfunctionIso11783PDDOnDefaultLogRequest.md) to activate the default logging.

## Parameters

- **ecuHandle**: Handle of the ECU, must previously have been created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).
- **command**: Measurement command:
  - 4: Time Interval
  - 5: Distance Interval
  - 6: Minimum within Threshold
  - 7: Maximum within Threshold
  - 8: Change Threshold
- **ddi**: Data Dictionary Identifier, 0x0000..0xFFFF
- **elNum**: Element number, 0x000..0xFFF
- **value**: Depends on `command`
  - **Time Interval**: time in ms
  - **Distance Interval**: distance in mm
  - **Minimum within Threshold / Maximum within Threshold / Change Threshold**: value of the process variable

Use value 0 to disable a trigger.

## Return Values

[error code](../CAPLfunctionsISONLErrorCodesPDDOnError.md)

## Example

```c
void Iso11783PDDOnDefaultLogRequest(dword ecuHandle) {
    Iso11783PDDSetLogTrigger(ecuHandle, 4, 0x0100, 0, 1000);
    Iso11783PDDSetLogTrigger(ecuHandle, 4, 0x0101, 0, 1000);
}
```
