[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestDisableMsgAllTx.md)

**CAPL Functions** » **Test Feature Set** » **TestDisableMsgAllTx**

# TestDisableMsgAllTx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestDisableMsgAllTx (char [] aNode)
```

## Description

Disables the sending of all tx messages of the node except the sending with [testSetMsgEvent](CAPLfunctionTestSetMsgEvent.md).

This function influences a simulation node with an assigned CANoe Interaction Layer or CANopen simulation.

**Note**

- Consider to set always the appropriate bus context in a multibus environment before the function is called.
- Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aNode**: Node, the tx messages should be disabled.

## Return Values

- **0**: No error.
- **-1**: General error.

## Example

```cpp
// send a message event for a message which is disabled by TestDisableMsgAllTx
TestDisableMsgAllTx(NodeToManipulate);
TestWaitForTimeout(5000);
TestSetMsgEvent(MsgToManipulate);
TestWaitForTimeout(5000);
TestEnableMsgAllTx(NodeToManipulate);
```

[TestEnableMsgAllTx](CAPLfunctionTestEnableMsgAllTx.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
