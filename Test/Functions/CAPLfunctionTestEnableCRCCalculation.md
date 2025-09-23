# TestEnableCRCCalculation

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
This function is not available for all OEM add-ons - depends on the CANoeIL.

## Function Syntax

```plaintext
long TestEnableCRCCalculation (dbMsg aMessage);
long TestEnableCRCCalculation (dword aMessageId);
long TestEnableCRCCalculation (char aMessageName[]);
```

## Description

Re-enables the calculation of the CRC, after it has been disabled with [TestDisableCRCCalculation](CAPLfunctionTestDisableCRCCalculation.md).

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

```plaintext
// resets the CRC calculation of message ‚MsgToManipulate’ to default behavior after a break of 2000 ms
TestDisableCRCCalculation(MsgToManipulate);
TestWaitForTimeout(2000);
TestEnableCRCCalculation(MsgToManipulate);
```
