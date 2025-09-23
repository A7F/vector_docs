[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPOnValueChange.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_OPOnValueChange**

# Iso11783IL_OPOnValueChange (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void Iso11783IL_OPOnValueChange( dword objectID );
```

## Description

The function is called by the node layer if the value of an object is changed (with the command Change String Value or Change Numeric Value). The functions [Iso11783IL_OPGetStringValue](CAPLfunctionIso11783ILOPGetStringValue.md) and [Iso11783IL_OPGetNumericValue](CAPLfunctionIso11783ILOPGetNumericValue.md) can be used to get the new value of the object.

## Parameters

- **objectID**: Object Identifier of the changed object

## Return Values

—

## Example

```plaintext
void Iso11783IL_OPOnValueChange( dword objectID )
{
}
```
