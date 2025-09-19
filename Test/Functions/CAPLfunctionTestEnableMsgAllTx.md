[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestEnableMsgAllTx.md)

# TestEnableMsgAllTx

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestEnableMsgAllTx

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestEnableMsgAllTx (char [] aNode);
```

## Description

Re-enables the sending of all tx messages of the node after having disabled it with [TestDisableMsgAllTx](CAPLfunctionTestDisableMsgAllTx.md).

This function influences a simulation node with an assigned CANoe Interaction Layer or CANopen simulation.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aNode**: Node, the tx messages should be enabled.

## Return Values

- **0**: No error.
- **-1**: General error.

## Example

```c
// send a message event for a message which is disabled by TestDisableMsgAllTx
// and re-enable the sending of all tx messages of node ‚NodeToManipulate’
TestDisableMsgAllTx(NodeToManipulate);
TestWaitForTimeout(5000);
TestSetMsgEvent(MsgToManipulate);
TestWaitForTimeout(5000);
TestEnableMsgAllTx(NodeToManipulate);
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
