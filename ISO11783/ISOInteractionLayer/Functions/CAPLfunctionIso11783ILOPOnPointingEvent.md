[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPOnPointingEvent.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_OPOnPointingEvent

# Iso11783IL_OPOnPointingEvent (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783IL_OPOnPointingEvent( long x, long y, dword state );
```

## Description

The function is called by the node layer, if the user clicks into the data mask.

## Parameters

- **x**: X position [pixel]
- **y**: Y position [pixel]
- **state**:
  - 0: Released (Version ≥ 3)
  - 1: Pressed (pressed)
  - 2: Held (Version ≥ 3)

## Return Values

—

## Example

```c
void Iso11783IL_OPOnPointingEvent( LONG x, LONG y, dword touchState )
{
}
```
