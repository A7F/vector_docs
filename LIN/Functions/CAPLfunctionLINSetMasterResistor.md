[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetMasterResistor.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetMasterResistor

# linSetMasterResistor

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long linSetMasterResistor (long onOff);
```

## Description

Enables or disables the internal master resistor of the LIN network interface.

**Note**: This function only works with LIN core network interfaces.

## Parameters

- **onOff**  
  1: Switch the resistor on  
  0: Switch the resistor off  

## Return Values

If successful a value unequal to zero.

## Example

```plaintext
// on pressing key ‘c’ switch on the master resisitor
...
on key 'c'
{
  linSetMasterResisitor (1);
  write("Turn Resistor On");
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
