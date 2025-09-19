[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestSetMsgCycleTime.md)

**CAPL Functions** » **Test Feature Set** » **TestSetMsgCycleTime**

# TestSetMsgCycleTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestSetMsgCycleTime(dbMsg aMessage, dword aNewCycleTime);`
- `long TestSetMsgCycleTime(dword aMessageId, dword aNewCycleTime);`
- `long TestSetMsgCycleTime(char aMessageName[], dword aNewCycleTime);`

## Description

Assigns a new cycle time to the message. This function influences a simulation node with an assigned CANoe Interaction Layer or CANopen simulation.

**Note**: Dependent on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: Message that should get a new cycle time.
- **aMessageId**: Numeric ID of the message that should get a new cycle time.
- **aNewCycleTime**: The new cycle time (in milliseconds) that should be assigned to the message.
- **aMessageName**: Name of the message that should get a new cycle time.
  - Message name can optionally be specified by additional qualifiers:
    - MsgName
    - BusName::MsgName
    - TransmitterName::MsgName
    - BusName::TransmitterName::MsgName

## Return Values

- **0**: No error
- **-1**: General error, for example, functionality is not available

## Example

```c
// set the cycle time of message ‘MsgToManipulate’ to a specified value for 2000 ms
TestSetMsgCycleTime(MsgToManipulate, 200);
TestWaitForTimeout(2000);
TestResetMsgCycleTime(MsgToManipulate);
```

**Related Functions**: [TestDisableMsg](CAPLfunctionTestDisableMsg.md) • [TestEnableMsg](CAPLfunctionTestEnableMsg.md) • [TestResetAllFaultInjections](CAPLfunctionTestResetAllFaultInjections.md) • [TestResetMsgCycleTime](CAPLfunctionTestResetMsgCycleTime.md) • [TestSetMsgEvent](CAPLfunctionTestSetMsgEvent.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
