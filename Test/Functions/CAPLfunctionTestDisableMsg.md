# TestDisableMsg

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
This function is not supported with [SOME/IP](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIP.md).

## Function Syntax

- `long TestDisableMsg (dbMsg aMessage);`
- `long TestDisableMsg (dword aMessageId);`
- `long TestDisableMsg (char aMessageName[]);`

## Description

Disables the sending of the message except by calling the function [TestSetMsgEvent](CAPLfunctionTestSetMsgEvent.md). Use [TestEnableMsg](CAPLfunctionTestEnableMsg.md) to re-enable the message.

This function influences a simulation node with an assigned CANoe Interaction Layer or CANopen simulation.

**Note**  
Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: Message that should be disabled.
- **aMessageId**: Numeric ID of the message that should be disabled.
- **aMessageName**: Name of the message that should be disabled.
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
// send a message event for the disabled message ‘MsgToManipulate’
TestDisableMsg(MsgToManipulate);
TestWaitForTimeout(5000);
TestSetMsgEvent(MsgToManipulate);
TestWaitForTimeout(5000);
TestEnableMsg(MsgToManipulate);
```

[TestResetAllFaultInjections](CAPLfunctionTestResetAllFaultInjections.md) • [TestResetMsgCycleTime](CAPLfunctionTestResetMsgCycleTime.md) • [TestSetMsgCycleTime](CAPLfunctionTestSetMsgCycleTime.md)
