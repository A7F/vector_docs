[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILControlStart.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_ControlStart**

# GBT27930IL_ControlStart

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_ControlStart();` // form 1
- `long GBT27930IL_ControlStart(dbNode node);` // form 2
- `long GBT27930IL_ControlStart(byte address);` // form 3
- `long GBT27930IL_ControlStart(dbNode node, byte address);` // form 4

## Description

The node starts the cyclic transmission of the configured messages.

The source address can be specified optionally. If it is not specified the node attribute [NmStationAddress](../../../../CANoeCANalyzer/J1939/j1939basics/j1939CanDbAttributes.md) must be defined.

## Parameters

- **address**: source address of the node (optional)
- **node**: Simulation node to apply the function

## Return Values

0 on success or [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on start
{
    GBT27930IL_ControlStart();
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)