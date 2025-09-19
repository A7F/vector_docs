[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILOnChangedState.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_OnChangedState

# TCIL_OnChangedState (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
void TCIL_OnChangedState( long state );
```

## Description

This callback function is called from the TC IL if it has changed its state.

## Parameters

- **state**
  - 0: Initialized
  - 1: Claiming
  - 2: Active
  - 3: Stopped
  - 4: Suspended

## Return Values

—

## Example

```c
void TCIL_OnChangedState( long state )
{
  switch(state) {
    case 1: // Claiming
      break;
    case 2: // Active
      break;
    case 3: // Stopped
      break;
    case 4: // Suspended
      break;
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
