[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILControlStop.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » GBT27930IL_ControlStop

# GBT27930IL_ControlStop

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_ControlStop();` // form 1
- `long GBT27930IL_ControlStop(dbNode node);` // form 2

## Description

Deactivates the IL and stops sending cyclic messages.

## Parameters

- **node**: Simulation node to apply the function

## Return Values

0 on success or [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 's'
{
    GBT27930IL_ControlStop(1);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
