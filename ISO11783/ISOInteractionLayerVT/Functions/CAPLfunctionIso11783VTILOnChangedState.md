[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILOnChangedState.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_OnChangedState

# VTIL_OnChangedState (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
void VTIL_OnChangedState( long state );
```

## Description

This callback function is called from the VT IL if it has changed its state.

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
void VTIL_OnChangedState( long state )
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

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
