[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDOnStateChanged.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_PDDOnStateChanged

# Iso11783IL_PDDOnStateChanged (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783IL_PDDOnStateChanged( 
 dword state );
```

## Description

Is called up when the interaction layer changes its state.

## Parameters

- **state**: task state:
  - 0: not initialized
  - 1: initialized
  - 2: start up delay (6 seconds)
  - 3: wait for task controller status
  - 4: query information
  - 5: transfer object pool
  - 6: object pool activation
  - 7: online
  - 8: task active

## Return Values

—

## Example

```c
void Iso11783IL_PDDOnStateChanged( dword state )
{
  switch(state) {
    case 0: // Uninitialized
      break;
    case 1: // Initialized
      break;
    case 2: // StartUpDelay
      break;
    case 3: // Wait For Task Controller Status
      break;
    case 4: // Query Info
      break;
    case 5: // Transfer Object Pool
      break;
    case 6: // Activate Object Pool
      break;
    case 7: // Online
      break;
    case 8: // Task active
      break;
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)