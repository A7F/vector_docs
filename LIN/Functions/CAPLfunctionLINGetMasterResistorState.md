[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetMasterResistorState.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetMasterResistorState

# linGetMasterResistorState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long linGetMasterResistorState();
```

## Description

Returns the internal master resistor’s current state of the LIN interface hardware.

**Note**: This function only works with LIN core network interfaces.

## Parameters

—

## Return Values

- **State of the master resistor**
  - 1: Resistor is on
  - 0: Resistor is off

## Example

```c
// on pressing key ‘c’ switch on the master resistor
...
on key 'c'
{
  long ret;
  ret = linGetMasterResistorState();
  write("Resistor State: %d", ret);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
