# ChkCreate_MsgRelCycleTimeViolation, ChkStart_MsgRelCycleTimeViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_MsgRelCycleTimeViolation (dbMsg aObservedMessage, double aMinRelCycleTime, double aMaxRelCycleTime, Callback aCallback); // form 1`
- `dword ChkStart_MsgRelCycleTimeViolation (dbMsg aObservedMessage, double aMinRelCycleTime, double aMaxRelCycleTime, Callback aCallback); // form 2`
- `dword ChkCreate_MsgRelCycleTimeViolation (dbMsg aObservedMessage, dword aSourceAddress, dword aDestinationAddress, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback); // form 3`
- `dword ChkStart_MsgRelCycleTimeViolation (dbMsg aObservedMessage, dword aSourceAddress, dword aDestinationAddress, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback); // form 4`
- `dword ChkCreate_MsgRelCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, Node aReceiveNode, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback); // form 5`
- `dword ChkStart_MsgRelCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, Node aReceiveNode, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback); // form 6`
- `dword ChkCreate_MsgRelCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback); // form 7`
- `dword ChkStart_MsgRelCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback); // form 8`
- `dword ChkCreate_MsgRelCycleTimeViolation(dword aMessageId, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback); // form 9`
- `dword ChkCreate_MsgRelCycleTimeViolation(char[] aMessageName, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback); // form 10`
- `dword ChkCreate_MsgRelCycleTimeViolation(dword aMessageId, double aMinRelCycleTime, double aMaxRelCycleTime); // form 11`
- `dword ChkStart_MsgRelCycleTimeViolation(dword aMessageId, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback); // form 12`
- `dword ChkStart_MsgRelCycleTimeViolation(char[] aMessageName, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback); // form 13`
- `dword ChkStart_MsgRelCycleTimeViolation(dword aMessageId, double aMinRelCycleTime, double aMaxRelCycleTime); // form 14`
- `dword ChkCreate_MsgRelCycleTimeViolation(long aMessageId, ethernetPort aEthernetPort, byte direction, dword vlanId, ip_Endpoint source, ip_Endpoint destination, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback); //form 15`
- `dword ChkCreate_MsgRelCycleTimeViolation(char[] aMessageName, ethernetPort aEthernetPort, byte direction, dword vlanId, ip_Endpoint source, ip_Endpoint destination, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback); //form 16`

## Constructor

- `TestCheck::CreateMsgRelCycleTimeViolation (dbMsg aObservedMessage, double aMinRelCycleTime, double aMaxRelCycleTime, Callback aCallback);`
- `TestCheck::StartMsgRelCycleTimeViolation (dbMsg aObservedMessage, double aMinRelCycleTime, double aMaxRelCycleTime, Callback aCallback);`
- `TestCheck::CreateMsgRelCycleTimeViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, double aMinRelCycleTime, double aMaxRelCycleTime, Callback aCallback);`
- `TestCheck::StartMsgRelCycleTimeViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, double aMinRelCycleTime, double aMaxRelCycleTime, Callback aCallback);`
- `TestCheck::CreateMsgRelCycleTimeViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, double aMinRelCycleTime, double aMaxRelCycleTime);`
- `TestCheck::StartMsgRelCycleTimeViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, double aMinRelCycleTime, double aMaxRelCycleTime);`
- `TestCheck::CreateMsgRelCycleTimeViolation (dbMsg aObservedMessage, dword aSourceAddress, dword aDestinationAddress, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback);`
- `TestCheck::StartMsgRelCycleTimeViolation (dbMsg aObservedMessage, dword aSourceAddress, dword aDestinationAddress, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback)`
- `TestCheck::CreateMsgRelCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, Node aReceiveNode, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback);`
- `TestCheck::StartMsgRelCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, Node aReceiveNode, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback);`
- `TestCheck::CreateMsgRelCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback);`
- `TestCheck::StartMsgRelCycleTimeViolation (dbMsg aObservedMessage, Node aSendNode, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback);`

## Check Name

[Cycle Time](../../../TestCommands/CheckDescriptions/CDCycleTime.md)

## Description

Checks the occurrences of cyclic messages.

Event is generated if the time between sends of the message is smaller than minRelCycleTime *GenMsgCycleTime (DB-attribute) or larger than maxRelCycleTime* GenMsgCycleTime.

Not to be checked limits are set to 0; there must be at least one limit specified.

Can be started only in the 'on start' section of CAPL or during measurement.

The numeric constructors with the parameter 'slotID' can only be applied to a FlexRay bus.

For FlexRay only valid data frames and PDUs are recognized as communication, Null Frames and Erroneous frames are ignored.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous.

Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aObservedMessage**: The observed message in symbolic form, e.g.: "MotorData", whose occurrence is to be monitored. Message must exist in database
- **aMinRelCycleTime**:
  - 0: Limit is not checked
  - 0 \< x \< 1: Limit is checked
- **aMaxRelCycleTime**:
  - 0: Limit is not checked
  - 1 \< x \< ∞: Limit is checked
- **aCallback**:
  - In simulation nodes this parameter has to be set.
  - In test modules this parameter is optional.
- **slotID**: This number designates a specific FlexRay slot. Its value must be between 1 and 2047.
- **cycleOffs**: This number designates the base cycle. This value must be smaller than the repetition factor and lies in the range between 0 and 63. This value, together with the repetition factor, determines the "Cycle Multiplexing" of a FlexRay frame.
- **cycleRep**: This number designates the cycle repetition factor. The value must be between 1 and 64 and be a multiple of 2 (e.g. 1, 2, 4, 8, 16, 32 or 64). This value, together with the base cycle, determines the "Cycle Multiplexing" of a FlexRay frame.
- **channelMask**: Identifies the FlexRay channel of the communication controller. A value of 1 will check the frame on channel A, 2 will check it on channel B and 3 on any channel (A/B).
- **aSourceAddress**: Source address of a J1939 parameter group. Possible values:
  - 0 – 253, 255: Observe parameter groups sent from this address.
  - 254: Observe parameter groups sent from any address.
  - 0xFFFFFFFF: Observe parameter groups sent from the source address which is specified by the parameter group in the database.
- **aDestinationAddress**: Destination address of a J1939 parameter group. Possible values:
  - 0 – 253, 255: Observe parameter groups sent to this address
  - 254: Observe parameter groups sent to any address
  - 0xFFFFFFFF: Observe parameter groups sent to the destination address which is specified by the parameter group in the database.
- **aSendNode**: Send node of a J1939 parameter group.
- **aReceiveNode**: Receive node of a J1939 parameter group. This parameter is only used for destination specific parameter groups (PDU1 format).
- **aMessageId**: The ID of the message whose cycle time is to be observed.
- **aMessageName**: The Name of the message whose cycle time is to be observed.
- **aEthernetPort**: Name of an Ethernet port. For example: "Network::Port"
- **vlanId**: VLAN ID
- **source**: Source IP address and port.
- **destination**: Destination IP address and port.
- **direction**: Direction of the specified PDU. Possible values:
  - 0: Rx only
  - 1: Tx only
  - 2: Rx and Tx

## Return Values

- **0**: Check could not be created and must not be referenced
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- Value range(s) exceeded
- Message object does not exist in DB
- Message object is not a cyclic message
- There are messages specified as cyclic but the cycle time is 0 or not available
- Both relative limits are 0
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)

## Example

```c
// checks the cycle time of the message
checkId = ChkStart_MsgRelCycleTimeViolation (MsgToObserve, 0.9, 1.1);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
