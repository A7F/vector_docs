[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOnChangedState.md)

## Iso11783IL_OnChangedState (Callback)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OnChangedState

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

```c
void Iso11783IL_OnChangedState( long state );
```

### Description

This callback function is called from the ISO11783 IL if it has changed its [state](../../../../CANoeCANalyzer/J1939/j1939IL/j1939ILStates.md).

### Parameters

- **state**
  - 0: Initialized
  - 1: Claiming
  - 2: Active
  - 3: Stopped
  - 4: Suspended

### Return Values

—

### Example

```c
void Iso11783IL_OnChangedState( LONG state )
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
