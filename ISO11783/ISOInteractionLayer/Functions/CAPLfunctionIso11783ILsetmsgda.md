[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILsetmsgda.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_SetMsgDA

# Iso11783IL_SetMsgDA

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_SetMsgDA( dbMsg dbMessage, dword destinationAddress );
```

## Description

Sets the message destination address.

## Parameters

- **dbMessage**: Message name as defined in the database
- **destinationAddress**: Destination address of the message

## Return Values

- **0**: Success
- **< 0**: [Error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
