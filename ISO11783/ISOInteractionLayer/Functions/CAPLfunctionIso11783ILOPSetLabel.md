[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPSetLabel.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPSetLabel

# Iso11783IL_OPSetLabel

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPSetLabel( dword objectID, dword stringVarIdD, dword fontType, dword graphID ); // form 1
long Iso11783IL_OPSetLabel( dbNode implement, dword objectID, dword stringVarIdD, dword fontType, dword graphID ); // form 2
```

## Description

A **Set Label** command is sent to the Virtual Terminal.

## Parameters

- **objectID**: object ID which is assigned to the label
- **stringVarID**: object ID of the string variable object
- **fontType**: font type
- **graphID**: object ID of a graphical object
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPSetLabel( 1200, 1250, 1, 1260 );
```
