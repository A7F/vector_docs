[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateMsgOccurrenceCount.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_MsgOccurrenceCount, ChkStart_MsgOccurrenceCount, TestCheck::CreateNodeMsgsOccurrenceCount, TestCheck::StartNodeMsgsOccurrenceCount

# ChkCreate_MsgOccurrenceCount, ChkStart_MsgOccurrenceCount, TestCheck::CreateNodeMsgsOccurrenceCount, TestCheck::StartNodeMsgsOccurrenceCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_MsgOccurrenceCount(dbMsg aMessage, long aMaxCount);`
- `dword ChkStart_MsgOccurrenceCount(dbMsg aMessage, long aMaxCount);`
- `dword ChkCreate_MsgOccurrenceCount(dword aMessageId, long aMaxCount);`
- `dword ChkStart_MsgOccurrenceCount(dword aMessageId, long aMaxCount);`
- `dword ChkCreate_MsgOccurrenceCount(dword aSourceAdr, dword aDestAdr, char[] aSymbolicMsg, dword aInstanceId, long aMaxCount)`
- `dword ChkStart_MsgOccurrenceCount(dword aSourceAdr, dword aDestAdr, char[] aSymbolicMsg, dword aInstanceId, long aMaxCount)`

## Constructor

- `TestCheck::CreateMsgOccurrenceCount(dbMsg aMessage, long aMaxCount);`
- `TestCheck::StartMsgOccurrenceCount(dbMsg aMessage, long aMaxCount);`
- `TestCheck::CreateMsgOccurrenceCount(dword aMessageId, long aMaxCount);`
- `TestCheck::StartMsgOccurrenceCount(dword aMessageId, long aMaxCount);`
- `TestCheck::CreateMsgOccurrenceCount(dword aSourceAdr, dword aDestAdr, char[] aSymbolicMsg, dword aInstanceId, long aMaxCount)`
- `TestCheck::StartMsgOccurrenceCount(dword aSourceAdr, dword aDestAdr, char[] aSymbolicMsg, dword aInstanceId, long aMaxCount)`
- `TestCheck::CreateMsgOccurrenceCount (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, dword aMaxCount)`
- `TestCheck::StartMsgOccurrenceCount (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, dword aMaxCount)`
- `TestCheck::CreateNodeMsgsOccurrenceCount (Node aNode, dword aMaxCount, char[] aCaplCallbackFunction)`
- `TestCheck::StartNodeMsgsOccurrenceCount (Node aNode, dword aMaxCount, char[] aCaplCallbackFunction)`
- `TestCheck::CreateNodeMsgsOccurrenceCount (Node aNode, dword aMaxCount)`
- `TestCheck::StartNodeMsgsOccurrenceCount (Node aNode, dword aMaxCount)`

## Check Name

[Occurrence Count](../../../TestCommands/CheckDescriptions/CDOccurrenceCount.md)

## Description

Checks the absence of the specified message on the bus. An event is created if more than **aMaxCount** of the specified message were sent.

The numeric functions/constructors with the parameter 'aMessageId/aSourceAdr' cannot be used for FlexRay. Instead use the numeric constructors with the parameter 'slotID' (that can only be applied to a FlexRay bus).

For FlexRay only valid data frames and PDUs are recognized as communication, Null Frames and Erroneous frames are ignored.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: The message in symbolic form, e.g.: "EngineData", whose occurrence is to be monitored. Message must exist in database.
- **aMessageId**: The ID of the message whose occurrence is to be monitored.
- **aMaxCount**: The maximum number of message that may be sent without the check to fail.
- **aSourceAdr**: The source address of the message whose occurrence is to be monitored.
- **aDestAdr**: The destination address of the message whose occurrence is to be monitored.
- **aSymbolicMsg**: Symbolic message definition of the message which has to be monitored in the format "FBlock.Function.OpType". Widcards can also be used (e.g. "AudioDiskPlayer.*.Status").
- **aInstanceId**: The instance ID of the message whose occurrence is to be monitored.
- **slotID**: This number designates a specific FlexRay slot. Its value must be between 1 and 2047.
- **cycleOffs**: This number designates the base cycle. This value must be smaller than the repetition factor and lies in the range between 0 and 63. This value, together with the repetition factor, determines the "Cycle Multiplexing" of a FlexRay frame.
- **cycleRep**: This number designates the cycle repetition factor. The value must be between 1 and 64 and be a multiple of 2 (e.g. 1, 2, 4, 8, 16, 32 or 64). This value, together with the base cycle, determines the "Cycle Multiplexing" of a FlexRay frame.
- **channelMask**: Identifies the FlexRay channel of the communication controller. A value of 1 will check the frame on channel A, 2 will check it on channel B and 3 on any channel (A/B).
- **aNode**: The node from the DB whose Tx messages should be observed.
- **aCaplCallbackFunction**: This parameter must be specified in simulation nodes; it is optional in test modules.

## Return Values

- **0**: Check could not be created and may not be referenced.
- **> 0**: Check was created successfully and can be referenced with the help of the returned (Handle) value.

## Check-specific Queries

- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)

## Example

```plaintext
// checks that the message is sent less than 3 times
checkId = ChkStart_MsgOccurrenceCount (MsgToObserve, 2);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
