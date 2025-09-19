[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILOnChangedState.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_OnChangedState

# FSIL_OnChangedState (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void FSIL_OnChangedState( long state );
```

## Description

Is called from the FS IL if it has changed its state.

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
void FSIL_OnChangedState( long state )
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

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
