[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestSetSetMsgDlc.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestSetMsgDlc

# TestSetMsgDlc

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestSetMsgDlc (dbMsg aMessage, dword dlc);`
- `long TestSetMsgDlc (dword aMessageId, dword dlc);`
- `long TestSetMsgDlc (char aMessageName[], dword dlc);`

## Description

The **Data-Length-Code (DLC)** or data length value for the specified message will be adjusted.

**Note**

- For CAN FD the DLC must be set.
- For the values 0-8, DLC and data length is the same value.
- For the values 9-15, DLC and data length differ:

  - **DLC 9**: Data Length CAN 8, Data Length CAN FD 12
  - **DLC 10**: Data Length CAN 8, Data Length CAN FD 16
  - **DLC 11**: Data Length CAN 8, Data Length CAN FD 20
  - **DLC 12**: Data Length CAN 8, Data Length CAN FD 24
  - **DLC 13**: Data Length CAN 8, Data Length CAN FD 32
  - **DLC 14**: Data Length CAN 8, Data Length CAN FD 48
  - **DLC 15**: Data Length CAN 8, Data Length CAN FD 64

This function influences a simulation node with an assigned CANoe Interaction Layer or CANopen simulation.

**Note**

Dependent on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: Message that should be manipulated.
- **aMessageId**: Numeric ID of the message that should be manipulated.
- **aMessageName**: Name of the message that should be manipulated.
  - Message name can optionally be specified by additional qualifiers:
    - MsgName
    - BusName::MsgName
    - TransmitterName::MsgName
    - BusName::TransmitterName::MsgName
- **dlc**: New DLC or data length that is assigned to the message.

## Return Values

- **0**: No error.
- **-1**: General error.

## Example

```c
// set the DLC of message ‘MsgToManipulate’ for 2000 ms to a specified length
TestSetMsgDLC(MsgToManipulate, 4);
TestWaitForTimeout(2000);
TestResetMsgDLC(MsgToManipulate);
```

[TestResetMsgDlc](CAPLfunctionTestResetMsgDlc.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
