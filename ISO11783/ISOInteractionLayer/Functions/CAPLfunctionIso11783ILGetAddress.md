[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILGetAddress.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_GetAddress**

# Iso11783IL_GetAddress

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_GetAddress(); // form 1
long Iso11783IL_GetAddress(dbNode node); // form 2
```

## Description

Returns the address that is used by the ISO11783 IL.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **≥ 0**: Address of the ISO11783 IL
- **< 0**: [Error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 'a'
{
  LONG addr;
  addr = Iso11783IL_GetAddress();
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
