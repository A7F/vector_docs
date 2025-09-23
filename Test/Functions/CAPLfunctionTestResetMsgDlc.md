# TestResetMsgDlc

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestResetMsgDlc (dbMsg aMessage);`
- `long TestResetMsgDlc (dword aMessageId);`
- `long TestResetMsgDlc (char aMessageName[]);`

## Description

Resets the DLC to the DLC of the database. This function influences a simulation node with an assigned CANoe Interaction Layer.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: Message symbol.
- **aMessageId**: Numeric ID of the message.
- **aMessageName**: Name of the message symbol. Message name can optionally specified by additional qualifiers:
  - MsgName
  - BusName::MsgName
  - TransmitterName::MsgName
  - BusName::TransmitterName::MsgName

## Return Values

- **0**: No error.
- **-1**: General error.

## Example

```c
// reset the DLC of message ‘MsgToManipulate’
TestSetMsgDLC(MsgToManipulate, 4);
TestWaitForTimeout(2000);
TestResetMsgDLC(MsgToManipulate);
```

[TestSetMsgDlc](CAPLfunctionTestSetSetMsgDlc.md)
