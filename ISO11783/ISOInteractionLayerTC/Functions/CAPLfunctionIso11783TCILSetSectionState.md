[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILSetSectionState.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_SetSectionState

# TCIL_SetSectionState

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_SetSectionState (dbNode client, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, dword sectionState); // form 1`
- `long TCIL_SetSectionState (dword addressClient, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, dword sectionState); // form 2`
- `long TCIL_SetSectionState (dbNode tc, dbNode client, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, dword sectionState); // form 3`
- `long TCIL_SetSectionState (dbNode tc, dword addressClient, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, dword sectionState); // form 4`

## Description

These functions set the state of a single section without sending any command.

For the already specified DDIs (currently in range DDI=0 and DDI=520), the functions check if the sectionNumber fits to the DDI.

The corresponding DDI (with states of 16 sections) can be sent with the methods [TCIL_ValueCommand](CAPLfunctionIso11783TCILValueCommandRawPhysical.md)/[TCIL_ValueAndAckCommand](CAPLfunctionIso11783TCILValueAndAckCommandRawPhysical.md).

## Parameters

- **tc**: Task Controller simulation node to apply the function.
- **client**: Task Controller client node the data entity belongs to.
- **addressClient**: Address of the Task Controller client node the data entity belongs to.
- **elementNumber**: Element number, 0x000..0xFFF.
- **ddiOfCondensedState**: Data dictionary identifier the condensed state belongs to, e.g.:
  - 161..176 (0x0A1..0x0B0) for **Actual Condensed Work State**
  - 290..305 (0x122..0x131) for **Setpoint Condensed Work State**
  - 367..382 (0x16F..0x17E) for **Condensed Section Override State**
  - 517 (0x205) for **Setpoint Tramline Condensed Work State 1-16**
  - 518 (0x206) for **Actual Tramline Condensed Work State 1-16**
- **sectionNumber**: Section number within the object, 1..256.
- **sectionState**: New section state, 0..3.
  - 0: disabled/off
  - 1: enabled/on
  - 2: error indicator
  - 3: no change

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 3

```c
void EnableSomeSections ()
{
  long result;
  // Sections 1, 3, 20 and 21 has to be enabled
  // All sections belong to the elementNumber=7
  // the first two sections belong to the DDI=290
  // the last two sections belong to the DDI=291

  TCIL_SetSectionState(TC, Sprayer, 290, 7, 1, 1);
  TCIL_SetSectionState(TC, Sprayer, 290, 7, 3, 1);
  TCIL_SetSectionState(TC, Sprayer, 291, 7, 20, 1);
  TCIL_SetSectionState(TC, Sprayer, 291, 7, 21, 1);

  // each DDI has to be sent with a single command
  // the first two sections belong to the DDI=290
  TCIL_ValueCommand(TC, Sprayer, 290, 7);
  // the last two sections belong to the DDI=291
  TCIL_ValueCommand(TC, Sprayer, 291, 7);
}
```
