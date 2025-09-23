[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryEventSignalValuePositive.md)

## ChkQuery_EventSignalValue (for signals with positive values)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_EventSignalValue (for signals with positive values)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

```plaintext
double ChkQuery_EventSignalValue (dword checkId);
```

### Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
check.QueryEventSignalValue();
```

### Description

This function enables access to the signal value which was last reported by a check as invalid. This function enables access only to positive signal values.

### Parameters

- **checkId**: Identifier of the queried Check.

### Return Values

- **< 0**: Refers the query error codes in this chapter
- **≥ 0**: Retrieved signal value

### Available For

- [ChkCreate_MsgSignalValueRangeViolation](CAPLfunctionChkCreateMsgSignalValueRangeViolation.md): Result: Value of the last signal that was bad
- [ChkCreate_MsgSignalValueInvalid](CAPLfunctionChkCreateMsgSignalValueInvalid.md): Result: Value of the last signal that was bad

### Example

```plaintext
double result;
dword checkId;
checkId = ChkStart_MsgSignalValueInvalid(Velocity, 80, 100);
// ... execute test sequence
result = ChkQuery_EventSignalValue(checkId);
```
