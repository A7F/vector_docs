[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangeActiveMask.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPChangeActiveMask

# Iso11783IL_OPChangeActiveMask

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPChangeActiveMask( dword maskID ); // form 1
long Iso11783IL_OPChangeActiveMask( dbNode implement, dword maskID ); // form 2
```

## Description

This function changes the active data mask. The **Change Active Mask** command is sent to the Virtual Terminal.

## Parameters

- **maskID**: object ID of the data mask object, which should be activated
- **implement**: Simulation node to apply the function.

## Return Values

- **= 0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPChangeActiveMask( 1000 );
```
