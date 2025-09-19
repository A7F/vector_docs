[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestCheckCreateMsgSendCountViolation.md)

## CAPL Functions » Test Service Library » Checks » TestCheck::CreateMsgSendCountViolation, TestCheck::StartMsgSendCountViolation, TestCheck::CreateNodeMsgSendCountViolation, TestCheck::StartNodeMsgSendCountViolation

### Valid for: CANoe DE • CANoe4SW DE

### Constructor

- `TestCheck::CreateMsgSendCountViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, dword aMinCount, dword aMaxCount, Duration aInterval, char[] aCaplCallbackFunction);`
- `TestCheck::StartMsgSendCountViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, dword aMinCount, dword aMaxCount, Duration aInterval, char[] aCaplCallbackFunction);`
- `TestCheck::CreateMsgSendCountViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, dword aMinCount, dword aMaxCount, Duration aInterval);`
- `TestCheck::StartMsgSendCountViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, dword aMinCount, dword aMaxCount, Duration aInterval);`
- `TestCheck::CreateMsgSendCountViolation (dbMsg aMessage, dword aMinCount, dword aMaxCount, Duration aInterval, char[] aCaplCallbackFunction);`
- `TestCheck::StartMsgSendCountViolation (dbMsg aMessage, dword aMinCount, dword aMaxCount, Duration aInterval, char[] aCaplCallbackFunction);`
- `TestCheck::CreateMsgSendCountViolation (dbMsg aMessage, dword aMinCount, dword aMaxCount, Duration aInterval);`
- `TestCheck::StartMsgSendCountViolation (dbMsg aMessage, dword aMinCount, dword aMaxCount, Duration aInterval);`
- `TestCheck::CreateNodeMsgSendCountViolation (Node aNode, dword aMinCount, dword aMaxCount, Duration aInterval, char[] aCaplCallbackFunction);`
- `TestCheck::StartNodeMsgSendCountViolation (Node aNode, dword aMinCount, dword aMaxCount, Duration aInterval, char[] aCaplCallbackFunction);`
- `TestCheck::CreateNodeMsgSendCountViolation (Node aNode, dword aMinCount, dword aMaxCount, Duration aInterval);`
- `TestCheck::StartNodeMsgSendCountViolation (Node aNode, dword aMinCount, dword aMaxCount, Duration aInterval);`

### Check Name

[Message Count Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMessageCountObservation.md)

### Description

Monitors the bus and reports if at least **aMinCount** and at most **aMaxCount** for each of the defined messages occurred within a specified time interval **aInterval**. If a DB node is used as reference, then all its Tx frames are observed. For FlexRay only valid data frames and PDUs are recognized as communication, Null Frames and Erroneous frames are ignored.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

### Parameters

- **slotID**: This number designates a specific FlexRay slot. Its value must be between 1 and 2047.
- **cycleOffs**: This number designates the base cycle. This value must be smaller than the repetition factor and lies in the range between 0 and 63. This value, together with the repetition factor, determines the "Cycle Multiplexing" of a FlexRay frame.
- **cycleRep**: This number designates the cycle repetition factor. The value must be between 1 and 64 and be a multiple of 2 (e.g. 1, 2, 4, 8, 16, 32 or 64). This value, together with the base cycle, determines the "Cycle Multiplexing" of a FlexRay frame.
- **channelMask**: Identifies the FlexRay channel of the communication controller. A value of 1 will check the frame on channel A, 2 will check it on channel B and 3 on any channel (A/B).
- **aMinCount**: The minimum number of message that must be sent without the check to fail.
- **aMaxCount**: The maximum number of message that may be sent without the check to fail. ('0' means infinite number.)
- **aInterval**: Defines the cyclic repeating time period in which the minimum and maximum number of defined messages must occur without the check failing. The unit can be set with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).
- **aNode**: The node from the DB whose Tx messages should be observed.
- **aMessage**: The message in symbolic form, e.g.: "EngineData", whose occurrence is to be monitored. Message must exist in database.
- **aCaplCallbackFunction**: This parameter must be specified in simulation nodes; it is optional in test modules.

### Return Values

- **0**: Check could not be created and may not be referenced.
- **> 0**: Check was created successfully and can be referenced with the help of the returned (Handle) value.

### Example

```plaintext
variables
{
  const dword cTesttime = 640; // [ms] per check

  // Frames that are sent by node Controller_Node_1:
  FrFrame MsgChannel1.Sync_Message_1_Ch_A      frame2;
  FrFrame MsgChannel1.Sync_Message_1_Ch_B      frame2b;
  FrFrame MsgChannel1.TimeSync_Message_1_Ch_A  frame15;

  const dword cFrFlagTT      = 0x00;
  const dword cFrFlagET      = 0x10;
  const dword cFrFlagStop    = 0x80;
}

testcase GoodCheckNodeMsgSendCountViolation_1 ()
{
  TestCheck c;
  dword cMinCount = 1;
  dword cMaxCount = 0; // ignore
  dword cInterval = 320; // [ms]

  // Assure check to succeed:
  frame2.FR_Flags = cFrFlagTT; // start sending the frame
  FRUpdateStatFrame(frame2);
  frame2b.FR_Flags = cFrFlagTT; // start sending the frame
  FRUpdateStatFrame(frame2b);
  frame15.FR_Flags = cFrFlagTT; // start sending the frame
  FRUpdateStatFrame(frame15);
  TestWaitForTimeout(330);

  c = TestCheck::CreateNodeMsgSendCountViolation( Controller_Node_1, cMinCount, cMaxCount, cInterval );

  TestAddCondition(c);

  c.start();
  TestWaitForTimeout(cTesttime);

  TestRemoveCondition(c);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
