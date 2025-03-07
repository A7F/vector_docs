[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestCheckCreateFlexRayNullFrameOccurrenceCount.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » TestCheck::CreateFlexRayNullFrameOccurrenceCount, TestCheck::StartFlexRayNullFrameOccurrenceCount, TestCheck::CreateNodeFlexRayNullFramesOccurrenceCount, TestCheck::StartNodeFlexRayNullFramesOccurrenceCount

# TestCheck::CreateFlexRayNullFrameOccurrenceCount, TestCheck::StartFlexRayNullFrameOccurrenceCount, TestCheck::CreateNodeFlexRayNullFramesOccurrenceCount, TestCheck::StartNodeFlexRayNullFramesOccurrenceCount

**Valid for**: CANoe DE • CANoe4SW DE

## Constructor

- `TestCheck::CreateFlexRayNullFrameOccurrenceCount (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, dword aMaxCount, char[] aCaplCallbackFunction);`
- `TestCheck::StartFlexRayNullFrameOccurrenceCount (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, dword aMaxCount, char[] aCaplCallbackFunction);`
- `TestCheck::CreateFlexRayNullFrameOccurrenceCount (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, dword aMaxCount);`
- `TestCheck::StartFlexRayNullFrameOccurrenceCount (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, dword aMaxCount);`
- `TestCheck::CreateFlexRayNullFrameOccurrenceCount (dbMsg aMessage, dword aMaxCount, char[] aCaplCallbackFunction);`
- `TestCheck::StartFlexRayNullFrameOccurrenceCount (dbMsg aMessage, dword aMaxCount, char[] aCaplCallbackFunction);`
- `TestCheck::CreateFlexRayNullFrameOccurrenceCount (dbMsg aMessage, dword aMaxCount);`
- `TestCheck::StartFlexRayNullFrameOccurrenceCount (dbMsg aMessage, dword aMaxCount);`
- `TestCheck::CreateNodeFlexRayNullFramesOccurrenceCount (Node aNode, dword aMaxCount, char[] aCaplCallbackFunction);`
- `TestCheck::StartNodeFlexRayNullFramesOccurrenceCount (Node aNode, dword aMaxCount, char[] aCaplCallbackFunction);`
- `TestCheck::CreateNodeFlexRayNullFramesOccurrenceCount (Node aNode, dword aMaxCount);`
- `TestCheck::StartNodeFlexRayNullFramesOccurrenceCount (Node aNode, dword aMaxCount);`

## Check Name

[Absence of FlexRay Null Frames (Check Description)](../../../TestCommands/CheckDescriptions/CDAbsenceOfFlexRayNullFrames.md)

## Description

Checks the absence of Null Frames for the specified frame/slot on the bus. An event is created if more than **aMaxCount** of the specified Null Frames were sent.

If a DB node is used as reference, then all its Tx frames are observed.

The numerical functions allow to define a wildcard event by setting slotID = -1, cycleOffs = 0, cycleRep = 1 in order to check for the absence of any FlexRay Null Frame.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **slotID**: This number designates a specific FlexRay slot. Its value must be between 1 and 2047.
- **cycleOffs**: This number designates the base cycle. This value must be smaller than the repetition factor and lies in the range between 0 and 63. This value, together with the repetition factor, determines the "Cycle Multiplexing" of a FlexRay frame.
- **cycleRep**: This number designates the cycle repetition factor. The value must be between 1 and 64 and be a multiple of 2 (e.g. 1, 2, 4, 8, 16, 32 or 64). This value, together with the base cycle, determines the "Cycle Multiplexing" of a FlexRay frame.
- **channelMask**: Identifies the FlexRay channel of the communication controller. A value of 1 will check the frame on channel A, 2 will check it on channel B and 3 on any channel (A/B).
- **aMaxCount**: The maximum number of message that may be sent without the check to fail.
- **aNode**: The node from the DB whose Tx messages should be observed.
- **aMessage**: The message in symbolic form, e.g.: "EngineData", whose occurrence is to be monitored. Message must exist in database.
- **aCaplCallbackFunction**: This parameter must be specified in simulation nodes; it is optional in test modules.

## Return Values

Object of type **TestCheck**.

## Check-specific Queries

- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)

## Example

```plaintext
variables
{
  const dword cTesttime = 640; // [ms] per check

  FrFrame MsgChannel1.(10,0,2) frame10 = { FR_Flags = 0, FR_ChannelMask = 1, FR_PayloadLength = 2 };

  const dword cFrFlagTT      = 0x00;
  const dword cFrFlagET      = 0x10;
  const dword cFrFlagStop    = 0x80;
}

testcase GoodCheckFlexRayNullFrameOccurrenceCount_1 ()
{
  TestCheck c;
  long cMaxCount = 0;

  // Assure check to succeed:
  frame10.FR_Flags = cFrFlagStop; // stop sending the frame
  FRUpdateStatFrame(frame10);
  TestWaitForTimeout(12);

  c = TestCheck::CreateFlexRayNullFrameOccurrenceCount( frame10.FR_SlotID, frame10.FR_CycleOffset, frame10.FR_CycleRepetition, frame10.FR_ChannelMask, cMaxCount);

  TestAddCondition(c);

  c.start();
  TestWaitForTimeout(cTesttime);

  TestRemoveCondition(c);
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)