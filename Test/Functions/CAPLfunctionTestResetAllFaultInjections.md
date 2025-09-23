# TestResetAllFaultInjections

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestResetAllFaultInjections (dbNode aNode);
```

## Description

Reset all fault injections setting of a node.

**Note**  
Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aNode**: Node which fault injection settings should be reset.

## Return Values

- **0**: No error.
- **-1**: General error.

## Example

```c
// set some FaultInjections and reset them all
TestDisableMsg(MsgToManipulate1);
TestSetMsgCycleTime(MsgToManipulate2, 200);

TestWaitForTimeout(2000);

TestResetAllFaultInjections(NodeToManipulate);
```

[TestDisableMsg](CAPLfunctionTestDisableMsg.md) • [TestEnableMsg](CAPLfunctionTestEnableMsg.md) • [TestResetMsgCycleTime](CAPLfunctionTestResetMsgCycleTime.md) • [TestSetMsgCycleTime](CAPLfunctionTestSetMsgCycleTime.md) • [TestSetMsgEvent](CAPLfunctionTestSetMsgEvent.md)
