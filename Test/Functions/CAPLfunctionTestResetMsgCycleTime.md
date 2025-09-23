# TestResetMsgCycleTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestResetMsgCycleTime (dbMsg aMessage);`
- `long TestResetMsgCycleTime (dword aMessageId);`
- `long TestResetMsgCycleTime (char aMessageName[]);`

## Description

Resets the cycle time of the message to the database cycle time, after having changed it with `TestSetMsgCycleTime(...)`. This function influences a simulation node with an assigned CANoe Interaction Layer or CANopen simulation.

**Note**

Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: Message that should get the database cycle time.
- **aMessageId**: Numeric ID of the message that should get the database cycle time.
- **aMessageName**: Name of the message that should get the database cycle time. Message name can optionally specified by additional qualifiers:
  - MsgName
  - BusName::MsgName
  - TransmitterName::MsgName
  - BusName::TransmitterName::MsgName

## Return Values

- **0**: No error.
- **-1**: General error.

## Example

```cpp
// reset the cycle time of message ‘MsgToManipulate’
TestSetMsgCycleTime(MsgToManipulate, 200);
TestWaitForTimeout(2000);
TestResetMsgCycleTime(MsgToManipulate);
```

[TestDisableMsg](CAPLfunctionTestDisableMsg.md) • [TestEnableMsg](CAPLfunctionTestEnableMsg.md) • [TestResetAllFaultInjections](CAPLfunctionTestResetAllFaultInjections.md) • [TestSetMsgCycleTime](CAPLfunctionTestSetMsgCycleTime.md) • [TestSetMsgEvent](CAPLfunctionTestSetMsgEvent.md)
