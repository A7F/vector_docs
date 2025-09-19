[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateMsgRelOccurrenceViolation.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_MsgRelOccurrenceViolation, ChkStart_MsgRelOccurrenceViolation

# ChkCreate_MsgRelOccurrenceViolation, ChkStart_MsgRelOccurrenceViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_MsgRelOccurrenceViolation(dbMsg observedMsg, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback);`
- `dword ChkStart_MsgRelOccurrenceViolation(dbMsg observedMsg, double aMin-RelCycleTime, double aMaxRelCycleTime, char[] aCallback);`
- `dword ChkCreate_MsgRelOccurrenceViolation(dword aMessageId, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback)`
- `dword ChkStart_MsgRelOccurrenceViolation(dword aMessageId, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCllback)`

## Constructor

- `TestCheck::CreateMsgRelOccurrenceViolation(dbMsg observedMsg, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback);`
- `TestCheck::StartMsgRelOccurrenceViolation(dbMsg observedMsg, double aMin-RelCycleTime, double aMaxRelCycleTime, char[] aCallback);`
- `TestCheck::CreateMsgRelOccurrenceViolation(dword aMessageId, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback)`
- `TestCheck::StartMsgRelOccurrenceViolation(dword aMessageId, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCllback)`
- `TestCheck::CreateMsgRelOccurrenceViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCllback)`
- `TestCheck::StartMsgRelOccurrenceViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCllback)`
- `TestCheck::CreateMsgRelOccurrenceViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, double aMinRelCycleTime, double aMaxRelCycleTime)`
- `TestCheck::StartMsgRelOccurrenceViolation (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, double aMinRelCycleTime, double aMaxRelCycleTime)`

## Check Name

[Occurrence Of Messages (Check Description)](../../../TestCommands/CheckDescriptions/CDOccurrenceOfMessages.md)

## Description

Checks for the occurrence of a periodic message. The check condition is violated if the time between transmissions of the message is less than `aMinRelCycleTime * GenMsgDelayTime` or greater than `aMaxRelCycleTime * Cycle Time`. Cycle time is calculated from `GenMsgCycleTime` and `GenSigCycleTime`. Limits that should not be checked must be set to 0. At least one limit must be specified. Can only be started in the "on start" area of CAPL or during the measurement. However, the check may be set up as early as in the "pre start" area.

The numeric functions/constructors with the parameter 'aMessageId' cannot be used for FlexRay. Instead use the numeric constructors with the parameter 'slotID' (that can only be applied to a FlexRay bus).

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **observedMessage**: The observed message in symbolic form, e.g.: "EngineData", whose occurrence is to be monitored. Message must exist in database.
- **aMinRelCycleTime**:
  - 0: Limit is not checked.
  - 0 < x < 1: Limit is checked.
- **aMaxRelCycleTime**:
  - 0: Limit is not checked.
  - 1 < x < ∞: Limit is checked.
- **aCallback**: This parameter must be specified in simulation nodes; it is optional in test modules.
- **aMessageId**: message ID to be observed. The corresponding message shall be defined in the database.
- **slotID**: This number designates a specific FlexRay slot. Its value must be between 1 and 2047.
- **cycleOffs**: This number designates the base cycle. This value must be smaller than the repetition factor and lies in the range between 0 and 63. This value, together with the repetition factor, determines the "Cycle Multiplexing" of a FlexRay frame.
- **cycleRep**: This number designates the cycle repetition factor. The value must be between 1 and 64 and be a multiple of 2 (e.g. 1, 2, 4, 8, 16, 32 or 64). This value, together with the base cycle, determines the "Cycle Multiplexing" of a FlexRay frame.
- **channelMask**: Identifies the FlexRay channel of the communication controller. A value of 1 will check the frame on channel A, 2 will check it on channel B and 3 on any channel (A/B).

## Return Values

- **0**: Check could not be created and may not be referenced.
- **> 0**: Check was created successfully and can be referenced by the returned (Handle) value.

## Possible Errors

- Value(s) outside of value range(s).
- Specified message object does not exist in the database.
- Message object is not a periodic message.
- Messages were specified as periodic, but their cycle time is either 0 or unavailable.
- Both relative limits are 0.
- CAPL Callback does not exist.

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventMessageNam](CAPLfunctionChkQueryEventMessageName.md)

## Example

```c
// checks the periodic occurrence of the message
checkId = ChkStart_MsgRelOccurrenceViolation (MsgToObserve, 0.9, 1.1);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
