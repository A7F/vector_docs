# TestDisableCRCCalculation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function is not available for all OEM add-ons - depends on the CANoeIL.

## Function Syntax

- `long TestDisableCRCCalculation (dbMsg aMessage);`
- `long TestDisableCRCCalculation (dword aMessageId);`
- `long TestDisableCRCCalculation (char aMessageName[]);`

## Description

Disables the calculation of the CRC of a message. This function influences a simulation node with an assigned CANoe Interaction Layer.

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

```plaintext
// disables the CRC calculation of message ‚MsgToManipulate’ for 2000 ms
TestDisableCRCCalculation(MsgToManipulate);
TestWaitForTimeout(2000);
TestEnableCRCCalculation(MsgToManipulate);
```

[TestEnableCRCCalculation](CAPLfunctionTestEnableCRCCalculation.md)
