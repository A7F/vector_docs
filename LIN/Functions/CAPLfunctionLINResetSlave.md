[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINResetSlave.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linResetSlave

# linResetSlave

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long linResetSlave (); // form 1`
- `long linResetSlave(dword resetToLastConfiguration); // form 2`

## Description

This function resets the NAD (Node Address for Diagnostic) of the modeled Slave node and marks all its protected identifiers as invalid or it will load the last saved configuration if `resetToLastConfiguration` is set.

See [Notes to the way initial NAD is determined](../CAPLfunctionsLINInitialNad.md) to understand how initial NAD is determined in CANoe.

**Note**: If the CAPL-program calling this function does not model a LIN 2.x Slave node, then this function will have no effect.

## Parameters

- **resetToLastConfiguration**
  - `0`: perform a complete reset
  - non-zero: load last saved configuration

## Return Values

On success this function returns a value unequal to -1, otherwise -1.

## Example

Force Slave reset on a keyboard event

```plaintext
on key 'r'
{
    if ( linResetSlave() != -1) {
        // from now on the Slave node stops publishing responses 
        ...
    }
}
```

[linResetNAD](CAPLfunctionLINResetNad.md) • [linActivateResps](CAPLfunctionLINActivateResps.md) • [linDeactivateResps](CAPLfunctionLINDeactivateResps.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
