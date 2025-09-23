[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ilsetmsgpgn.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_SetMsgPGN**

# GBT27930IL_SetMsgPGN

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_SetMsgPGN(dbMsg dbMessage, dword priority ); // form 1
long GBT27930IL_SetMsgPGN(dbNode node, dbMsg dbMessage, dword pgn ); // form 2
```

## Description

Sets new value of PGN.

## Parameters

- **dbMessage**: Message name as defined in the database.
- **pgn**: New value of PGN.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
