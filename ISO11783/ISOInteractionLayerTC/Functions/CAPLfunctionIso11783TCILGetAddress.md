[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILGetAddress.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_GetAddress**

# TCIL_GetAddress

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_GetAddress(); // form 1
long TCIL_GetAddress(dbNode tc); // form 2
```

## Description

Returns the address that is used by the TC IL.

## Parameters

- **tc**: TC simulation node to apply the function

## Return Values

- **≥ 0**: Address of the TC IL
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example form 1**

```plaintext
on key 'a'
{
  long addr;
  addr = TCIL_GetAddress();
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)