[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPLoadAuxAssignment.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPLoadAuxAssignment

# Iso11783IL_OPLoadAuxAssignment

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPLoadAuxAssignment( char filename[] ); // form 1
long Iso11783IL_OPLoadAuxAssignment( dbNode implement, char filename[] ); // form 2
```

## Description

This function loads the **Preferred Auxiliary Input Assignment** from an INI file. If the ECU is active, the **Preferred Assignment Message** is sent immediately. Otherwise, it is sent if the ECU gets active.

The **Preferred Assignment** must be saved with [Iso11783IL_OPSaveAuxAssignment](CAPLfunctionIso11783ILOPSaveAuxAssignment.md) before.

## Parameters

- **filename**: Filename of an INI file
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPLoad( "ObjectPool.iop", "pool001"  );
Iso11783IL_OPLoadAuxAssignment( "Sprayer.INI");
Iso11783IL_OPActivate();
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
