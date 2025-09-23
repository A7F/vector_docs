[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPStoreVersion.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPStoreVersion

# Iso11783IL_OPStoreVersion

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPStoreVersion( char versionName[] ); // form 1
long Iso11783IL_OPStoreVersion( dbNode implement, char versionName[] ); // form 2
```

## Description

The function stores the current object pool on the Virtual Terminal. A **Store Version** command is sent to the Virtual Terminal.

## Parameters

- **versionName**: name which is used to store the object pool. For [VT version](CAPLfunctionIso11783ILOPSetProperty.md) smaller than 5 the name must be 7 characters long. For VT version 5 and higher a name with more than 7 characters is sent with the **Store Extended Version** command.
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPStoreVersion( "POOL01A" );
```
