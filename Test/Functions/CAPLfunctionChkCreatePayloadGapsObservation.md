[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreatePayloadGapsObservation.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_PayloadGapsObservation, ChkStart_PayloadGapsObservation

# ChkCreate_PayloadGapsObservation, ChkStart_PayloadGapsObservation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_PayloadGapsObservation(dbMsg aMessage, long defaultBitValue, char [] aCallback);`
- `dword ChkStart_PayloadGapsObservation(dbMsg aMessage, long defaultBitValue, char [] aCallback);`
- `dword ChkCreate_PayloadGapsObservation(dword aMessageId, long defaultBitValue, char [] aCallback);`
- `dword ChkStart_PayloadGapsObservation(dword aMessageId, long defaultBitValue, char [] aCallback);`
- `dword ChkCreate_PayloadGapsObservation(dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, long defaultBitValue, char [] aCallback);`
- `dword ChkStart_PayloadGapsObservation(dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, long defaultBitValue, char [] aCallback);`

## Constructor

- `TestCheck::CreatePayloadGapsObservation(dbMsg aMessage, long defaultBitValue, char [] aCallback);`
- `TestCheck::StartPayloadGapsObservation(dbMsg aMessage, long defaultBitValue, char [] aCallback);`
- `TestCheck::CreatePayloadGapsObservation(dword aMessageId, long defaultBitValue, char [] aCallback);`
- `TestCheck::StartPayloadGapsObservation(dword aMessageId, long defaultBitValue, char [] aCallback);`
- `TestCheck::CreatePayloadGapsObservation(dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, long defaultBitValue, char [] aCallback);`
- `TestCheck::StartPayloadGapsObservation(dword slotID, dword cycleOffs, dword cycleRep, dword channelMask, long defaultBitValue, char [] aCallback);`

## Check Name

[Payload Gaps Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDPayloadGapsObservation.md)

## Description

Checks the payload gaps and the DLC of a message.

The check condition is violated if the payload gaps do not match the specified default bit value or the DLC does not match the specified DLC of the database.

The numeric functions/constructors with the parameter **aMessageId** cannot be used for FlexRay. Instead use the numeric constructors with the parameter **slotID** (that can only be applied to a FlexRay bus).

For FlexRay only valid data frames and PDUs are recognized as communication, Null Frames and Erroneous Frames are ignored.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous.

Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: The message in symbolic form, e.g.: "EngineData", whose occurrence is to be monitored. Message must exist in database.
- **defaultBitValue**: Default bit value the payload gaps must have.
- **aCallback**: This parameter must be specified in simulation nodes; it is optional in test modules.
- **aMessageId**: Message ID to be observed. The corresponding message shall be defined in the database.
- **slotID**: This number designates a specific FlexRay slot. Its value must be between 1 and 2047.
- **cycleOffs**: This number designates the base cycle. This value must be smaller than the repetition factor and lies in the range between 0 and 63. This value, together with the repetition factor, determines the "Cycle Multiplexing" of a FlexRay frame.
- **cycleRep**: This number designates the cycle repetition factor. The value must be between 1 and 64 and be a multiple of 2 (e.g. 1, 2, 4, 8, 16, 32 or 64). This value, together with the base cycle, determines the "Cycle Multiplexing" of a FlexRay frame.
- **channelMask**: Identifies the FlexRay channel of the communication controller. A value of 1 will check the frame on channel A, 2 will check it on channel B and 3 on any channel (A/B).

## Return Values

- **0**: Check could not be created and must not be referenced.
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Specified message object does not exist in the database.
- CAPL Callback does not exist.

## Example

```plaintext
// checks the payload gaps of the message
checkId = ChkStart_PayloadGapsObservation(MsgToObserve, 0);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)