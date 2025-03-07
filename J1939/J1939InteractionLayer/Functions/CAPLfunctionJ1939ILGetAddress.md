[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILGetAddress.md)

**CAPL Functions** » **J1939** » **J1939 IL** » **J1939ILGetAddress**

# J1939ILGetAddress

[Valid for: CANoe DE • CANoe4SW DE](../../../../Shared/FeatureAvailability.md)

## Function Syntax

- `long J1939ILGetAddress(); // form 1`
- `long J1939ILGetAddress(dbNode node); // form 2`

## Description

Returns the address that is used by the J1939 IL.

## Parameters

- **node**: Simulation node to apply the function

## Return Values

- **≥ 0**: address of the J1939 IL
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```c
on key 'a'
{
  LONG addr;
  addr = J1939ILGetAddress();
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)