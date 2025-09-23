[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPSetProperty.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPSetProperty

# Iso11783IL_OPSetProperty

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPSetProperty( char propertyName[], long newValue ); // form 1
long Iso11783IL_OPSetProperty( dbNode implement, char propertyName[], long newValue ); // form 2
```

## Description

The function sets a property of the Object Pool API, i.e. the supported Virtual Terminal version.

## Parameters

- **propertyName**: Key of the information to set:
  - **Version**: Supported version of the ISO11783 Virtual Terminal specification. Supported values: 2, 3 (default), 4 and 5. If used, the version value obtained from the database (node attribute ISO11783OPVersion) is overwritten.
  - **SendPreferredAssignmentEvenIfEmpty**: Enforces sending of the **Preferred Assigning** message to the Virtual Terminal, even if no auxiliary function has a preferred assigned auxiliary input. Supported values:
    - 0: **Preferred Assigning** message is sent to the Virtual Terminal if at least one preferred assignment exists.
    - 1: **Preferred Assigning** message is sent to the Virtual Terminal even if no preferred assignment exists.
  - **VTFunctionInstance**: On startup the node connects to the Virtual Terminal (VT) which has this function instance. By default, the node connects to the primary VT with function instance zero (0). If value -1 is used then the node connects to the first visible VT.
  - **ModelIdentificationCode**: Model identification code of the implement which is sent in the **Auxiliary Input Type 2 Maintenance** message.

- **newValue**: New value for the parameter.

- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **-102**: Invalid parameter
- **-1113**: Unknown property

## Example

```plaintext
Iso11783IL_OPSetProperty( "Version", 3 );
```
