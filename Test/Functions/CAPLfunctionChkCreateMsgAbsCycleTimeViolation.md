[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateMsgAbsCycleTimeViolation.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_MsgAbsCycleTimeViolation, ChkStart_MsgAbsCycleTimeViolation

# ChkCreate_MsgAbsCycleTimeViolation, ChkStart_MsgAbsCycleTimeViolation

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_MsgAbsCycleTimeViolation (dbMsg aObservedMessage, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback); // form 1`
- `dword ChkStart_MsgAbsCycleTimeViolation (dbMsg aObservedMessage, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback); // form 2`
- `dword ChkCreate_MsgAbsCycleTimeViolation (dbMsg aObservedMessage, dword aSourceAddress, dword aDestinationAddress, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback); // form 3`
- `dword ChkStart_MsgAbsCycleTimeViolation (dbMsg aObservedMessage, dword aSourceAddress, dword aDestinationAddress, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback); // form 4`
- `dword ChkCreate_MsgAbsCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, Node aReceiveNode, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback); // form 5`
- `dword ChkStart_MsgAbsCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, Node aReceiveNode, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback); // form 6`
- `dword ChkCreate_MsgAbsCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback); // form 7`
- `dword ChkStart_MsgAbsCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback); // form 8`
- `dword ChkCreate_MsgAbsCycleTimeViolation (long MessageId, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback); // form 9`
- `dword ChkStart_MsgAbsCycleTimeViolation (long MessageId, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback); // form 10`
- `dword ChkCreate_MsgAbsCycleTimeViolation(long MessageId, long aEthernetPortId, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback); // form 11`
- `dword ChkStart_MsgAbsCycleTimeViolation(long MessageId, long aEthernetPortId, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback); // form 12`
- `dword ChkCreate_MsgAbsCycleTimeViolation(long MessageId, char[] aEthernetPort, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback); // form 13`
- `dword ChkStart_MsgAbsCycleTimeViolation(long MessageId, char[] aEthernetPort, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback); // form 14`
- `dword ChkCreate_MsgAbsCycleTimeViolation(char[] aMessageName, long aEthernetPortId, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback); // form 15`
- `dword ChkStart_MsgAbsCycleTimeViolation(char[] aMessageName, long aEthernetPortId, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback); // form 16`
- `dword ChkCreate_MsgAbsCycleTimeViolation(char[] aMessageName, char[] aEthernetPort, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback); // form 17`
- `dword ChkStart_MsgAbsCycleTimeViolation(char[] aMessageName, char[] aEthernetPort, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback); // form 18`
- `dword ChkCreate_MsgAbsCycleTimeViolation(long MessageId, long aEthernetPortId, duration aMinAbsCycleTime, duration aMaxAbsCycleTime); // form 19`
- `dword ChkStart_MsgAbsCycleTimeViolation(long MessageId, long aEthernetPortId, duration aMinAbsCycleTime, duration aMaxAbsCycleTime); // form 20`
- `dword ChkCreate_MsgAbsCycleTimeViolation(long MessageId, char[] aEthernetPort, duration aMinAbsCycleTime, duration aMaxAbsCycleTime); // form 21`
- `dword ChkStart_MsgAbsCycleTimeViolation(long MessageId, char[] aEthernetPort, duration aMinAbsCycleTime, duration aMaxAbsCycleTime); // form 22`
- `dword ChkCreate_MsgAbsCycleTimeViolation(dbMsg aObservedMessage, long aEthernetPortId, duration aMinAbsCycleTime, duration aMaxAbsCycleTime); // form 23`
- `dword ChkStart_MsgAbsCycleTimeViolation(dbMsg aObservedMessage, long aEthernetPortId, duration aMinAbsCycleTime, duration aMaxAbsCycleTime); // form 24`
- `dword ChkCreate_MsgAbsCycleTimeViolation(dbMsg aObservedMessage, char[] aEthernetPort, duration aMinAbsCycleTime, duration aMaxAbsCycleTime); // form 25`
- `dword ChkStart_MsgAbsCycleTimeViolation(dbMsg aObservedMessage, char[] aEthernetPort, duration aMinAbsCycleTime, duration aMaxAbsCycleTime); // form 26`
- `dword ChkCreate_MsgAbsCycleTimeViolation(dbMsg aObservedMessage, long aEthernetPortId, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback); // form 27`
- `dword ChkStart_MsgAbsCycleTimeViolation(dbMsg aObservedMessage, long aEthernetPortId, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback); // form 28`
- `dword ChkCreate_MsgAbsCycleTimeViolation(dbMsg aObservedMessage, char[] aEthernetPort, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback); // form 29`
- `dword ChkStart_MsgAbsCycleTimeViolation(dbMsg aObservedMessage, char[] aEthernetPort, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback); // form 30`
- `dword ChkCreate_MsgAbsCycleTimeViolation(char[] aMessageName, dword aMinAbsCycleTime, dword aMaxAbsCycleTime, char[] aCallback); //form 31`
- `dword ChkStart_MsgAbsCycleTimeViolation(char[] aMessageName, dword minAbsCycleTime, dword maxAbsCycleTime, char[] caplCallbackFunction); //form 32`
- `dword ChkStart_MsgAbsCycleTimeViolation(dbMsg aObservedMessage, dword vlanId, ip_Endpoint source, ip_Endpoint destination, dword aMinAbsCycleTime, dword aMaxAbsCycleTime, char[] aCallback); //form 33`
- `dword ChkStart_MsgAbsCycleTimeViolation(dbMsg aObservedMessage, dword vlanId, ip_Endpoint source, ip_Endpoint destination, dword aMinAbsCycleTime, dword aMaxAbsCycleTime); //form 34`
- `dword ChkCreate_MsgAbsCycleTimeViolation(long MessageId, ethernetPort aEthernetPort, byte direction, dword vlanId, ip_Endpoint source, ip_Endpoint destination, dword aMinAbsCycleTime, dword aMaxAbsCycleTime, char[] aCallback); //form 35`
- `dword ChkCreate_MsgAbsCycleTimeViolation(char[] aMessageName, ethernetPort aEthernetPort, byte direction, dword vlanId, ip_Endpoint source, ip_Endpoint destination, dword aMinAbsCycleTime, dword aMaxAbsCycleTime, char[] aCallback); //form 36`

## Constructor

[TestCheck::CreateMsgAbsCycleTimeViolation (dbMsg aObservedMessage, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback);](../../../Shared/CAPL/General/ClassesAndObjects.htm)

- `TestCheck::StartMsgAbsCycleTimeViolation (dbMsg aObservedMessage, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback);`
- `TestCheck::CreateMsgAbsCycleTimeViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback);`
- `TestCheck::StartMsgAbsCycleTimeViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, duration aMinAbsCycleTime, duration aMaxAbsCycleTime, char[] aCallback);`
- `TestCheck::CreateMsgAbsCycleTimeViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, duration aMinAbsCycleTime, duration aMaxAbsCycleTime);`
- `TestCheck::StartMsgAbsCycleTimeViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, duration aMinAbsCycleTime, duration aMaxAbsCycleTime);`
- `TestCheck::CreateMsgAbsCycleTimeViolation (dbMsg aObservedMessage, dword aSourceAddress, dword aDestinationAddress, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback);`
- `TestCheck::StartMsgAbsCycleTimeViolation (dbMsg aObservedMessage, dword aSourceAddress, dword aDestinationAddress, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback);`
- `TestCheck::CreateMsgAbsCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, Node aReceiveNode, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback);`
- `TestCheck::StartMsgAbsCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, Node aReceiveNode, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback);`
- `TestCheck::CreateMsgAbsCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback);`
- `TestCheck::StartMsgAbsCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, duration aMinCycleTime, duration aMaxCycleTime, char[] aCallback);`

## Check Name

[Cycle Time](../../../TestCommands/CheckDescriptions/CDCycleTime.md)

## Description

Checks the occurrences of cyclic messages. Event is generated if the time between sends of the message is smaller than aMinCycleTime or larger than aMaxCycleTime. Not to be checked limits are set to 0; there must be at least on limit specified. Can be started only in the 'on start' section of CAPL or during measurement. The numeric constructors with the parameter 'slotID' can only be applied to a FlexRay bus. For FlexRay only valid data frames and PDUs are recognized as communication, Null Frames and Erroneous frames are ignored.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aObservedMessage**: The observed message in symbolic form, e.g.: "MotorData", whose occurrence is to be monitored. Message must exist in database.
- **aMinCycleTime**:
  - 0: Limit is not checked
  - 0 < x < aMaxCycleTime: Limit is checked
  - Default unit [ms], if not changed with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).
- **aMaxCycleTime**:
  - 0: Limit is not checked
  - aMinCycleTime < x < ∞: Limit is checked
  - Default unit [ms], if not changed with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).
- **aCallback**:
  - In simulation nodes this parameter has to be set.
  - In test modules this parameter is optional.
- **slotID**:
  - This number designates a specific FlexRay slot.
  - Its value must be between 1 and 2047.
- **cycleOffs**:
  - This number designates the base cycle.
  - This value must be smaller than the repetition factor and lies in the range between 0 and 63.
  - This value, together with the repetition factor, determines the "Cycle Multiplexing" of a FlexRay frame.
- **cycleRep**:
  - This number designates the cycle repetition factor.
  - The value must be between 1 and 64 and be a multiple of 2 (e.g. 1, 2, 4, 8, 16, 32 or 64).
  - This value, together with the base cycle, determines the "Cycle Multiplexing" of a FlexRay frame.
- **channelMask**: Identifies the FlexRay channel of the communication controller. A value of 1 will check the frame on channel A, 2 will check it on channel B and 3 on any channel (A/B).
- **aSourceAddress**: Source address of a J1939 parameter group. Possible values:
  - 0 – 253, 255: Observe parameter groups sent from this address.
  - 254: Observe parameter groups sent from any address.
  - -1 (or 0xFFFFFFFF): Observe parameter groups sent from the source address which is specified by the parameter group in the database.
- **aDestinationAddress**: Destination address of a J1939 parameter group. Possible values:
  - 0 – 253, 255: Observe parameter groups sent to this address
  - 254: Observe parameter groups sent to any address
  - -1 (or 0xFFFFFFFF): Observe parameter groups sent to the destination address which is specified by the parameter group in the database.
- **aSendNode**: Send node of a J1939 parameter group.
- **aReceiveNode**: Receive node of a J1939 parameter group. This parameter is only used for destination specific parameter groups (PDU1 format).
- **MessageId**: Message-ID of an A429 Label.
- **aMessageName**: Name of a message or PDU.
- **aEthernetPort**: Name of an Ethernet port. For example: "Network::Port"
- **aEthernetPortId**: ID of an Ethernet port.
- **vlanId**: VLAN ID
- **source**: Source IP address and port.
- **destination**: Destination IP address and port.
- **direction**: Direction of the specified PDU. Possible values:
  - 0: Rx only
  - 1: Tx only
  - 2: Rx and Tx

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- Message object does not exist in DB
- Both relative limits are 0
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)

## Example

```cpp
// checks the cycle time of the message
checkId = ChkStart_MsgAbsCycleTimeViolation (MsgToObserve, 90, 110);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
