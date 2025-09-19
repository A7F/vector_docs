[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateInconsistentDlc.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_InconsistentDLC, ChkStart_InconsistentDLC

# ChkCreate_InconsistentDLC, ChkStart_InconsistentDLC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_InconsistentDLC(dbMsg aMessage, char [] aCallback);`
- `dword ChkStart_InconsistentDLC(dbMsg aMessage, char [] aCallback);`
- `dword ChkCreate_InconsistentDlc(dword aMessageId, char aCallback[]);`
- `dword ChkStart_InconsistentDlc(dword aMessageId, char aCallback[]);`

## Constructor

- `TestCheck::CreateInconsistentDLC(dbMsg aMessage, char [] aCallback);`
- `TestCheck::StartInconsistentDLC(dbMsg aMessage, char [] aCallback);`
- `TestCheck::CreateInconsistentDlc(dword aMessageId, char aCallback[]);`
- `TestCheck::StartInconsistentDlc(dword aMessageId, char aCallback[]);`
- `TestCheck::CreateInconsistentDlc (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, char[] aCallback);`
- `TestCheck::StartInconsistentDlc (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, char[] aCallback);`
- `TestCheck::CreateInconsistentDlc (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask);`
- `TestCheck::StartInconsistentDlc (dword slotID, dword cycleOffs, dword cycleRep, dword channelMask);`

## Check Name

[DLC](../../../TestCommands/CheckDescriptions/CDDLC.md)

## Description

Checks the DLC, respectively the payload length of a message. The check condition is violated if the DLC of the message does not agree with the specified DLC of the database. Can only be started in the "on start" area of CAPL or during the measurement. However, the check may be set up as early as in the "pre start" area.

The numeric functions/constructors with the parameter 'aMessageId' cannot be used for FlexRay. Instead use the numeric constructors with the parameter 'slotID' (that can only be applied to a FlexRay bus).

For FlexRay only valid data frames and PDUs are recognized as communication, Null Frames and Erroneous frames are ignored.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: The message in symbolic form, e.g.: "EngineData", whose occurrence is to be monitored. Message must exist in database.
- **aCallback**: This parameter must be specified in simulation nodes; it is optional in test modules.
- **aMessageId**: Message ID to be observed. The corresponding message shall be defined in the database.
- **slotID**: This number designates a specific FlexRay slot. Its value must be between 1 and 2047.
- **cycleOffs**: This number designates the base cycle. This value must be smaller than the repetition factor and lies in the range between 0 and 63. This value, together with the repetition factor, determines the "Cycle Multiplexing" of a FlexRay frame.
- **cycleRep**: This number designates the cycle repetition factor. The value must be between 1 and 64 and be a multiple of 2 (e.g. 1, 2, 4, 8, 16, 32 or 64). This value, together with the base cycle, determines the "Cycle Multiplexing" of a FlexRay frame.
- **channelMask**: Identifies the FlexRay channel of the communication controller. A value of 1 will check the frame on channel A, 2 will check it on channel B and 3 on any channel (A/B).

## Return Values

- **0**: Check could not be created and may not be referenced.
- **> 0**: Check was created successfully and can be referenced with the help of the returned (Handle) value.

## Possible Errors

- Specified message object does not exist in the database.
- CAPL Callback does not exist.

## Example

```plaintext
// checks the DLC of the message
checkId = ChkStart_InconsistentDlc (MsgToObserve);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
