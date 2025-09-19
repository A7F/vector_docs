[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOnAddressClaimConflict.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OnAddressClaimConflict

# Iso11783IL_OnAddressClaimConflict (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783IL_OnAddressClaimConflict(dword addressArbitrationResult, dword nextAddress, dword& suppressAddressClaimed);
```

## Description

This callback function is called by any interaction layer that detects an address conflict. A conflict occurs if another node sends an **Address Claim Message** from the same address with or without preceding request. Additionally, the callback is called when an ISOBUS Interaction Layer sends a **Request for Address Claim** at initialization time and its preferred address is already used, regardless of the priority of the device name.

If the IL is **Arbitrary Address Capable** the parameter **nextAddress** is set to the next available address beginning with 0x80, else **nextAddress** is set to 0xFE (Null Address). If the arbitration is won, **nextAddress** is set to current (preferred) address.

This callback can be used to define custom rules for address resolution and to override the suggested address.

To use the callback, make sure the ILs property **AddressClaimSupport** is set to **ExtendedAddressClaimSupport** (2).

## Parameters

- **addressArbitrationResult**
  - 0: Arbitration won
  - 1: Arbitration lost
  - 2: Address already in use an current ECU won
  - 3: Address already in use and current ECU lost

- **nextAddress**
  - The address the IL will claim if not overridden.

- **suppressAddressClaimed**
  - Set to 1, if the ACL message shall be suppressed.

## Return Values

- **0..254**
  - The new address that shall be claimed.

## Example

```c
variables
{
  byte lastUsedAddress = 0x80;

  enum AddressClaimSupport
  {
    NoAddressClaimSupport        = 0,
    BasicAddressClaimSupport     = 1,
    ExtendedAddressClaimSupport  = 2
  };
}

on preStart
{
  Iso11783IL_SetNodeProperty("AddressClaimSupport", ExtendedAddressClaimSupport);
}

dword Iso11783IL_OnAddressClaimConflict(dword addressArbitrationResult, dword nextAddress, dword& suppressAddressClaimed)
{
  if (addressArbitrationResult == 1 || addressArbitrationResult == 3)
  {
    if(lastUsedAddress < 0xFE)
    {
      // calculate new address and return it so the IL uses it for address claiming
      lastUsedAddress++;
      write("Node_A claims new address %u", lastUsedAddress);
      return lastUsedAddress;
    }
  }
  return nextAddress;
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
