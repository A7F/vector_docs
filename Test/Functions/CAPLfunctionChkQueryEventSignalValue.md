# ChkQuery_EventSignalValue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long ChkQuery_EventSignalValue (dword checkId, double pValue[]); // form 1`
- `long ChkQuery_EventSignalValue (dword checkId, int64& value); // form 2`

## Method Syntax

- `check.QueryEventSignalValue (double pValue[]); // form 1`
- `check.QueryEventSignalValue (int64& value); // form 2`

## Description

This function enables access to the signal value which was last reported by a check as invalid. The signature of the function with the same name without the pValue parameter enables access only to positive signal values. This function enables access to signal values in any directory.

## Parameters

- **checkId**: Identifier of the queried Check.
- **double *pValue**:
  - Note: This requires the transfer of an array.

## Return Values

- `\<= 0`: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md) in this chapter

## Available For

- [ChkCreate_MsgSignalValueRangeViolation](CAPLfunctionChkCreateMsgSignalValueRangeViolation.md): Result: Value of the last signal that was bad
- [ChkCreate_MsgSignalValueInvalid](CAPLfunctionChkCreateMsgSignalValueInvalid.md): Result: Value of the last signal that was bad

## Example

```c
CallbackOnSignalXyzViolation(dword aCheckId)
{
   double lBadValue[1]; // use an array to allow "call-by-reference"; length: 1 element
   ChkQuery_EventSignalValue(aCheckId, lBadValue);
   write("Last bad signal value=%g", lBadValue[0]);
}
```
