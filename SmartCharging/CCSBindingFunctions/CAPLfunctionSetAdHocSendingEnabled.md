# SetAdHocSendingEnabled

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » SetAdHocSendingEnabled

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

`MethodReturnValueType SetAdHocSendingEnabled ( long Enable )`

## Description

This function allows manual sending of messages by updating at least one of their values.

## Parameters

- **Enable**: 1 = enable, 0 = disable

## Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0`: OK
- `1`: InvalidArgument
- `2`: NoMatchingElementFound
- `3`: UnknownError

## Example

—
