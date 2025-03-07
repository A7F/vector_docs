[J1939ILOnChangedState](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILOnChangedState.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILOnChangedState

# J1939ILOnChangedState (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void J1939ILOnChangedState( long state )
```

## Description

This callback function is called from the J1939 IL if it has changed its [state](../../../../CANoeCANalyzer/J1939/j1939IL/j1939ILStates.md).

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

```plaintext
void J1939ILOnChangedState( LONG state )
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