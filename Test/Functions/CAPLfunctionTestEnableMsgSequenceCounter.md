# TestEnableMsgSequenceCounter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function is not available for all OEM add-ons - depends on the CANoeIL.

## Function Syntax

- `long TestEnableMsgSequenceCounter (dbMsg aMessage);`
- `long TestEnableMsgSequenceCounter (dword aMessageId);`
- `long TestEnableMsgSequenceCounter (char aMessageName[]);`

## Description

Re-enables the message sequence counter, after it has been disabled with [TestDisableMsgSequenceCounter](CAPLfunctionTestDisableMsgSequenceCounter.md).

This function influences a simulation node with an assigned CANoe Interaction Layer.

**Note**  
Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous.  
Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: Message that should be reset to default behavior.
- **aMessageId**: Numeric ID of the message that should be reset to default behavior.
- **aMessageName**: Name of the message that should be reset to default behavior.
  - Message name can optionally specified by additional qualifiers:
    - MsgName
    - BusName::MsgName
    - TransmitterName::MsgName
    - BusName::TransmitterName::MsgName

## Return Values

- **0**: No error.
- **-1**: General error.

## Example

```c
// disables the message sequence counter of message ‚MsgToManipulate’ for 2000ms
// and re-enables the message sequence counter afterwards
TestDisableMsgSequenceCounter(MsgToManipulate);
TestWaitForTimeout(2000);
TestEnableMsgSequenceCounter(MsgToManipulate);
```
