[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILsetmsgcycletime.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_SetMsgCycleTime

# Iso11783IL_SetMsgCycleTime

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_SetMsgCycleTime( dbMsg dbMessage, dword cycleTime );
```

## Description

Sets the message cycle time in ms.

## Parameters

- **dbMessage**: Message name as defined in the database
- **cycleTime**: Cycle time in ms

## Return Values

- **0**: Success
- **< 0**: [Error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
