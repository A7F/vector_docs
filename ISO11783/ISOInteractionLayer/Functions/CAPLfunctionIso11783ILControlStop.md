[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILControlStop.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_ControlStop

# Iso11783IL_ControlStop

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_ControlStop();` // form 1
- `long Iso11783IL_ControlStop( dword option );` // form 2
- `long Iso11783IL_ControlStop( dbNode node );` // form 3
- `long Iso11783IL_ControlStop( dbNode node, dword option );` // form 4

## Description

Deactivates the IL and stops sending cyclic messages. A [Cannot Claim Address](../../../../CANoeCANalyzer/J1939/j1939basics/j1939NMT.md) message is sent, if the NMT is activated and the message is not suppressed with the parameter `option` set to 1.

## Parameters

- **option**: Options  
  1: Suppress sending **Cannot Claim Address** message.

- **node**: Simulation node to apply the function.

## Return Values

0 on success or [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 's'
{
    Iso11783IL_ControlStop(1);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)