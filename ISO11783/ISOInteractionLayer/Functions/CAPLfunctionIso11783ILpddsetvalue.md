[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILpddsetvalue.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_PDDSetValue

# Iso11783IL_PDDSetValue

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_PDDSetValue( dbSignal signal, dword elementNumber, float value ); // form 1`
- `long Iso11783IL_PDDSetValue( dword ddi, dword elementNumber, float value ); // form 2`
- `long Iso11783IL_PDDSetValue( dbNode implement, dword ddi, dword elementNumber, float value ); // form 3`

## Description

Sets the value of a process variable.

## Parameters

- **signal**: signal from the database. The attribute **ddi** must have been defined for the signal. The signal must be defined in the same database as the node!
- **ddi**: Data Dictionary Identifier, 0x0000.0xFFFF
- **elementNumber**: element number, 0x000.0xFFF
- **value**: new value of the process variable
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred

## Example

```plaintext
Iso11783IL_PDDSetValue( 0x200. 3, value );
Iso11783IL_PDDSetValue( 0x200. 4, value );
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
