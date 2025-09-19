[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILEnableNameManagement.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_EnableNameManagement

# Iso11783IL_EnableNameManagement

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `dword Iso11783IL_EnableNameManagement(dword enable); // form 1`
- `dword Iso11783IL_EnableNameManagement(dword enable, dword bitMask); // form 2`
- `dword Iso11783IL_EnableNameManagement(dbNode node, dword enable); // form 3`
- `dword Iso11783IL_EnableNameManagement(dbNode node, dword enable, dword bitMask); // form 4`

## Description

This function activates the name management of a node. Not until the name management is activated another node can change the device name of this node by sending a name management message.

## Parameters

- **enable**
  - `1`: activate the name management
  - `0`: deactivates the name management

- **bitmask**
  - Parts of the device name that are allowed to be changed:
    - bit 0 (LSB): Arbitrary Address Capable
    - bit 1: Industry Group
    - bit 2: System Instance
    - bit 3: System
    - bit 4: Function
    - bit 5: Function Instance
    - bit 6: ECU Instance
    - bit 7 (MSB): Manufacturer Code

- **node**
  - Simulation node to apply the function.

## Return Values

`0` on success or [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```c
// allow every component to be changed except arbitrary address capable flag
Iso11783IL_EnableNameManagement(1, 0xFE);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
