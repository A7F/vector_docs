[J1939ILGetState](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILGetState.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILGetState

# J1939ILGetState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILGetState(); // form 1
long J1939ILGetState(dbNode node); // form 2
```

## Description

Returns the current state of the J1939 IL.

## Parameters

- **node**: Simulation node to apply the function

## Return Values

- **0**: Initialized
- **1**: Claiming
- **2**: Active
- **3**: Stopped
- **4**: Suspended
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 's'
{
  LONG state;
  state = J1939ILGetState();
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
