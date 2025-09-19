[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILGetSectionState.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_GetSectionState**

# TCIL_GetSectionState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_GetSectionState (dbNode client, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, dword& sectionState); // form 1`
- `long TCIL_GetSectionState (dword addressClient, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, dword& sectionState); // form 2`
- `long TCIL_GetSectionState (dbNode tc, dbNode client, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, dword& sectionState); // form 3`
- `long TCIL_GetSectionState (dbNode tc, dword addressClient, dword ddiOfCondensedState, dword elementNumber, dword sectionNumber, dword& sectionState); // form 4`

## Description

These functions return the current state of a single section. For the already specified DDIs (currently in range DDI=0 and DDI=520), the functions check if the sectionNumber fits to the DDI.

## Parameters

- **tc**: Task Controller simulation node to apply the function.
- **client**: Task Controller client node the data entity belongs to.
- **addressClient**: Address of Task Controller client node the data entity belongs to.
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

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 3

```c
dword IsSectionEnabled(dword elementNumber, dword sectionNumber)
{
  long result;
  dword state;
  result = TCIL_GetSectionState(TC, Sprayer, 161, elementNumber, sectionNumber, state);
  if (result < 0)
  {
    TestStepFail("Failed to get current state!");
    return result;
  }
  return (state == 1);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
