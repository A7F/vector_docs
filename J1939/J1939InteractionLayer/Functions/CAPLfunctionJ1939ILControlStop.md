[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILControlStop.md)

**CAPL Functions** » **J1939** » **J1939 IL** » **J1939ILControlStop**

# J1939ILControlStop

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILControlStop(); // form 1`
- `long J1939ILControlStop(dbNode node); // form 2`
- `long J1939ILControlStop(dword options); // form 3`
- `long J1939ILControlStop(dbNode node, dword options); // form 4`

## Description

Deactivates the IL and stops sending cyclic messages.

A [Cannot Claim Address](../../../../CANoeCANalyzer/J1939/j1939basics/j1939NMT.md) message is sent, if the [NMT is activated](../../../../CANoeCANalyzer/J1939/j1939IL/j1939ILActivateFeatures.md) and the message is not suppressed with the parameter `option` set to 1.

## Parameters

- **options**:
  - `1`: suppress sending **Cannot Claim Address** message
- **node**: Simulation node to apply the function

## Return Values

`0` on success or [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 's'
{
    J1939ILControlStop(1);
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
