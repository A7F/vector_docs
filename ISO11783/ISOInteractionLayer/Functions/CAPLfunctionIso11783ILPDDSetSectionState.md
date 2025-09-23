[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDSetSectionState.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_PDDSetSectionState

# Iso11783IL_PDDSetSectionState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_PDDSetSectionState(dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, dword sectionState); // form 1
long Iso11783IL_PDDSetSectionState(dbNode implement, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, dword sectionState); // form 2
```

## Description

Sets the state of a single section.

For the already specified DDIs (currently in range DDI=0 and DDI=520), the functions check if the sectionNumber fits to the DDI.

## Parameters

- **ddiOfCondensedState**: Data dictionary identifier the condensed state belongs to, e.g.:
  - 161..176 (0x0A1..0x0B0) for Actual Condensed Work State
  - 290..305 (0x122..0x131) for Setpoint Condensed Work State
  - 367..382 (0x16F..0x17E) for Condensed Section Override State
  - 517 (0x205) for Setpoint Tramline Condensed Work State 1-16
  - 518 (0x206) for Actual Tramline Condensed Work State 1-16

- **elementNumber**: Element number, 0x000..0xFFF.

- **sectionNumber**: Section number within the object, 1..256.

- **sectionState**:
  - 0: disabled/off
  - 1: enabled/on
  - 2: error indicator
  - 3: no change

- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
long result;
char text[256];
result = Iso11783IL_PDDSetSectionState(290, 10, 1, 1);
if (result < 0)
{
  Iso11783IL_GetLastErrorText ( elCount(text), text );
  write( "ERROR: %s", text);
}
```
