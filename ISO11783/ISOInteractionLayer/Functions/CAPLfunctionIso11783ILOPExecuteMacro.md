[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPExecuteMacro.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPExecuteMacro

# Iso11783IL_OPExecuteMacro

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPExecuteMacro( dword macroID ); // form 1
long Iso11783IL_OPExecuteMacro( dbNode implement, dword macroID ); // form 2
```

## Description

The function executes a macro object. An **Execute Macro** command is sent to the Virtual Terminal.

## Parameters

- **macroID**: object ID of a macro object
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPExecuteMacro( 1200 );
```
