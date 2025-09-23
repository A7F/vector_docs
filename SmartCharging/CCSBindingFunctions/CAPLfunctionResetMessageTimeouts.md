# ResetMessageTimeouts

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » ResetMessageTimeouts

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

`MethodReturnValueType ResetMessageTimeouts ( )`

## Description

This function resets all message timeouts to their respective defaults.

## Parameters

—

## Return Values

### MethodReturnValueType

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- 0: OK
- 1: InvalidArgument
- 2: NoMatchingElementFound
- 3: UnknownError

## Example

—
