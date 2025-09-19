[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILControlStart.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_ControlStart

# Iso11783IL_ControlStart

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_ControlStart(); // form 1`
- `long Iso11783IL_ControlStart( byte address ); // form 2`
- `long Iso11783IL_ControlStart( dbNode node ); // form 3`
- `long Iso11783IL_ControlStart( dbNode node, byte address ); // form 4`

## Description

The node starts Address Claiming (if NMT is activated). If the Address Claiming was successful, cyclic messages are sent.

The source address can be specified optionally. If it is not specified the node attribute **NmStationAddress** must be defined.

## Parameters

- **address**: Source address of the node (optional).
- **node**: Simulation node to apply the function.

## Return Values

0 on success or [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on start
{
    Iso11783IL_ControlStart();
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
