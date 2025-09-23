# ChkQuery_EventMessageName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
double ChkQuery_EventMessageName (dword aCheckId, char buffer[], dword bufferlen);
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
check.QueryEventMessageName (char buffer[], dword bufferlen);
```

## Description

Stores the name of the message, that has led to the event, in the buffer and returns 0 if specified for a range or error code.

## Parameters

- **aCheckId** —
- **buffer** —
- **bufferlen** —

## Return Values

- **\<= 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)

## Available For

- [ChkCreate_MsgDistViolation](CAPLfunctionChkCreateMsgDistViolation.md): Result: the last message with a bad distance
- [ChkCreate_MsgRelCycleTimeViolation](CAPLfunctionChkCreateMsgRelCycleTimeViolation.md): Result: the observed message
- [ChkCreate_MsgRelOccurrenceViolation](CAPLfunctionChkCreateMsgRelOccurrenceViolation.md): Result: the last message with a bad cycle time
- [ChkCreate_NodeMsgsRelCycleTimeViolation](CAPLfunctionChkCreateNodeMsgsRelCycleTimeViolation.md): Result: the last message with a bad cycle time
- [ChkCreate_NodeMsgsRelOccurrenceViolation](CAPLfunctionChkCreateNodeMsgsRelOccurrenceViolation.md): Result: the last message with a bad cycle time
- [ChkCreate_NodeBabbling](CAPLfunctionChkCreateNodeBabbling.md): Result: the message sent by the observed node
- [ChkCreate_MsgSignalValueRangeViolation](CAPLfunctionChkCreateMsgSignalValueRangeViolation.md): Result: the observed message
- [ChkCreate_MsgSignalValueInvalid](CAPLfunctionChkCreateMsgSignalValueInvalid.md): Result: the observed message
- [ChkStart_LINRespErrorSignal](CAPLfunctionChkStartLinRespErrorSignal.md): Result: the name of the LIN frame carrying fired the Response_Error signal
- [ChkStart_LINRespToleranceViolation](CAPLfunctionChkStartLinRespToleranceViolation.md): Result: the name of the last LIN frame with violated response length
- [ChkStart_SignalValueChange](CAPLfunctionChkCreateSignalValueChange.md): Result: the observed signal
- [ChkStart_MsgAbsCycleTimeViolation](CAPLfunctionChkCreateMsgAbsCycleTimeViolation.md): Result: the observed message
- [ChkStart_SignalCycleTimeViolation](CAPLfunctionChkStartSignalCycleTimeViolation.md): Result: the name of the last frame with a bad signal cycle time
- [ChkStart_LINETFViolation](CAPLfunctionChkStartLinEtfViolation.md): Result: the name of the last LIN associated frame violating the process of collision resolution (if applicable)

## Example

```plaintext
long result;
dword checkId;
char messageName[100];
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = ChkQuery_EventMessageName(checkId, messageName, 100);
Write("result = %d", result);
```
