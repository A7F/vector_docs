[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryEventMessageId.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Status Report Functions](../CAPLfunctionsTSLStatusReportFunctions.md) » ChkQuery_EventMessageId

# ChkQuery_EventMessageId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ChkQuery_EventMessageId (dword aCheckId);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
check.QueryEventMessageId();
```

## Description

Returns the ID of the message that has forced the event.

## Parameters

- **aCheckId** —

## Return Values

- **< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **> 0**: ID of the name

## Available For

- [ChkCreate_MsgRelCycleTimeViolation](CAPLfunctionChkCreateMsgRelCycleTimeViolation.md): Result: the observed message
- [ChkCreate_NodeMsgsRelCycleTimeViolation](CAPLfunctionChkCreateNodeMsgsRelCycleTimeViolation.md): Result: the last message with a bad cycle time
- [ChkCreate_MsgDistViolation](CAPLfunctionChkCreateMsgDistViolation.md): Result: the last message with a bad distance
- [ChkCreate_MsgSignalValueRangeViolation](CAPLfunctionChkCreateMsgSignalValueRangeViolation.md): Result: the observed message
- [ChkCreate_MsgSignalValueInvalid](CAPLfunctionChkCreateMsgSignalValueInvalid.md): Result: the observed message
- [ChkStart_LINRespErrorSignal](CAPLfunctionChkStartLinRespErrorSignal.md): Result: the ID of the LIN frame carrying the fired Response_Error signal
- [ChkStart_LINHeaderToleranceViolation](CAPLfunctionChkStartLinHeaderToleranceViolation.md): Result: the ID of the last LIN frame with violated header length
- [ChkStart_LINSyncBreakTimingViolation](CAPLfunctionChkStartLinSyncBreakTimingViolation.md): Result: the ID of the last LIN frame with violated timing
- [ChkStart_LINSyncDelTimingViolation](CAPLfunctionChkStartLinSyncDelTimingViolation.md): Result: the ID of the last LIN frame with violated timing
- [ChkStart_LINRespToleranceViolation](CAPLfunctionChkStartLinRespToleranceViolation.md): Result: the ID of the last LIN frame with violated response length
- [ChkStart_SignalCycleTimeViolation](CAPLfunctionChkStartSignalCycleTimeViolation.md): Result: the ID of the last frame with a bad signal cycle time
- [ChkCreate_MsgOccurrenceCount](CAPLfunctionChkCreateMsgOccurrenceCount.md): Result: the ID of the last defined message that occurred
- [ChkStart_LINETFViolation](CAPLfunctionChkStartLinEtfViolation.md): Result: the ID of the last LIN associated frame violating the process of collision resolution (if applicable)

## Example

```plaintext
long result;
dword checkId;
checkId = ChkStart_MsgRelCycleTimeViolation(VehicleMotion, 0.9, 1.1);
// ... execute test sequence
result = ChkQuery_EventMessageId(checkId);
Write("result = %d", result);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
