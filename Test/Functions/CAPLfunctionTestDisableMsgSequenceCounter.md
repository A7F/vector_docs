[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestDisableMsgSequenceCounter.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestDisableMsgSequenceCounter

# TestDisableMsgSequenceCounter

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
This function is not available for all OEM add-ons - depends on the CANoeIL.

## Function Syntax

- `long TestDisableMsgSequenceCounter (dbMsg aMessage)`
- `long TestDisableMsgSequenceCounter (dword aMessageId)`
- `long TestDisableMsgSequenceCounter (char aMessageName[])`

## Description

Disables the message sequence counter. This function influences a simulation node with an assigned CANoe Interaction Layer.

**Note**  
Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: Message that should be manipulated.
- **aMessageId**: Numeric ID of the message that should be manipulated.
- **aMessageName**: Name of the message that should be manipulated.
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
// disables the message sequence counter of message ‘MsgToManipulate’ for 2000ms
TestDisableMsgSequenceCounter(MsgToManipulate);
TestWaitForTimeout(2000);
TestEnableMsgSequenceCounter(MsgToManipulate);
```

[TestEnableMsgSequenceCounter](CAPLfunctionTestEnableMsgSequenceCounter.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
