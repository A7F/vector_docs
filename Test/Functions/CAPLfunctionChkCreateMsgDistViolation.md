[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateMsgDistViolation.md)

**CAPL Functions** » **Test Service Library** » **Checks** » **ChkCreate_MsgDistViolation, ChkStart_MsgDistViolation**

# ChkCreate_MsgDistViolation, ChkStart_MsgDistViolation

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_MsgDistViolation (dbMsg aReferenceMessage, dbMsg aObservedMessage, duration aMinDistance, duration aMaxDistance, Callback aCallback); // form 1`
- `dword ChkStart_MsgDistViolation (dbMsg aReferenceMessage, dbMsg aObservedMessage, duration aMinDistance, duration aMaxDistance, Callback aCallback); // form 2`
- `dword ChkCreate_MsgDistViolation (dbMsg aReferenceMessage, char aReferenceBus[], dbMsg aObservedMessage, char aObservedBus[], duration aMinDistance, duration aMaxDistance, Callback aCallback); // form 3`
- `dword ChkStart_MsgDistViolation (dbMsg aReferenceMessage, char aReferenceBus[], dbMsg aObservedMessage, char aObservedBus[], duration aMinDistance, duration aMaxDistance, Callback aCallback); // form 4`
- `dword ChkCreate_MsgDistViolation(char[] aReferenceMessageName, char[] aObservedMessageName, duration aMinDistance, duration aMaxDistance, Callback aCallback); // form 5`
- `dword ChkCreate_MsgDistViolation(dword aReferenceMessageId, dword  aObservedMessageId, duration aMinDistance, duration aMaxDistance, Callback aCallback); // form 6`
- `dword ChkStart_MsgDistViolation(char[] aReferenceMessageName, char[] aObservedMessageName, duration aMinDistance, duration aMaxDistance, Callback aCallback); // form 7`
- `dword ChkStart_MsgDistViolation(dword aReferenceMessageId, dword  aObservedMessageId, duration aMinDistance, duration aMaxDistance, Callback aCallback); // form 8`

## Constructor

- `TestCheck::CreateMsgDistViolation (dbMsg aReferenceMessage, dbMsg aObservedMessage, duration aMinDistance, duration aMaxDistance, Callback aCallback);`
- `TestCheck::StartMsgDistViolation (dbMsg aReferenceMessage, dbMsg aObservedMessage, duration aMinDistance, duration aMaxDistance, Callback aCallback);`
- `TestCheck::CreateMsgDistViolation (dbMsg aReferenceMessage, char aReferenceBus[], dbMsg aObservedMessage, char aObservedBus[], duration aMinDistance, duration aMaxDistance, Callback aCallback);`
- `TestCheck::StartMsgDistViolation (dbMsg aReferenceMessage, char aReferenceBus[], dbMsg aObservedMessage, char aObservedBus[], duration aMinDistance, duration aMaxDistance, Callback aCallback);`
- `TestCheck::CreateMsgDistViolation (dword slotID1, dword cycleOffs1, dword cycleRep1, dword channelMask1, dword slotID2, dword cycleOffs2, dword cycleRep2, dword channelMask2, duration aMinDistance, duration aMaxDistance);`

## Check Name

[Message Distance (Check Description)](../../../TestCommands/CheckDescriptions/CDMessageDistance.md)

## Description

Event is generated if the time interval that starts on receipt of the reference message and ends with the receipt of the observed message is smaller than aMinDistance or is larger than aMaxDistance.

The numeric constructors with the parameter 'slotID1/2' can only be applied to a FlexRay bus.

For FlexRay only valid data frames and PDUs are recognized as communication, Null Frames and Erroneous frames are ignored.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aReferenceMessage**: The reference message in symbolic form, e.g.: "EngineData", whose occurrence is to be monitored. Message must exist in database.
- **aObservedMessage**: The observed message in symbolic form, e.g.: "MotorData", whose occurrence is to be monitored. Message must exist in database.
- **aMinDistance**: Default unit [ms], if not changed with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md). aMinDistance < aMaxDistance
- **aMaxDistance**: Default unit [ms], if not changed with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md). aMinDistance < aMaxDistance
- **aCallback**: In simulation nodes this parameter has to be set. In test modules this parameter is optional
- **aReferenceBus**: Name of the bus on that should be received the reference message
- **aObservedBus**: Name of the bus that should receive the observed message
- **slotID1/2**: This number designates a specific FlexRay slot. Its value must be between 1 and 2047.
- **cycleOffs1/2**: This number designates the base cycle. This value must be smaller than the repetition factor and lies in the range between 0 and 63. This value, together with the repetition factor, determines the "Cycle Multiplexing" of a FlexRay frame.
- **cycleRep1/2**: This number designates the cycle repetition factor. The value must be between 1 and 64 and be a multiple of 2 (e.g. 1, 2, 4, 8, 16, 32 or 64). This value, together with the base cycle, determines the "Cycle Multiplexing" of a FlexRay frame.
- **channelMask1/2**: Identifies the FlexRay channel of the communication controller. A value of 1 will check the frame on channel A, 2 will check it on channel B and 3 on any channel (A/B).
- **aReferenceMessageName**: The Name of the message whose distance is to be observed.
- **aObservedMessageName**: The Name of the message whose distance is to be observed.
- **aReferenceMessageId**: The ID of the message whose distance is to be observed.
- **aObservedMessageId**: The ID of the message whose distance is to be observed.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- Value range(s) exceeded
- Any specified message object do not exist in the DB
- CAPL callback does not exist
- Observed message received without preceding reference message
- Message Ids identical for **aReferenceMessage** and **aObservedMessage**, if both messages are expected at the same bus

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)

## Example

```c
// checks the distance between two messages
checkId = ChkStart_MsgDistViolation (ReferenceMsg, MsgToObserve, 90, 110);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
