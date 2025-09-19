[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILEnableNameManagement.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_EnableNameManagement**

# FSIL_EnableNameManagement

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword FSIL_EnableNameManagement(dword enable); // form 1`
- `dword FSIL_EnableNameManagement(dword enable, dword bitMask); // form 2`
- `dword FSIL_EnableNameManagement(dbNode fs, dword enable); // form 3`
- `dword FSIL_EnableNameManagement(dbNode fs, dword enable, dword bitMask); // form 4`

## Description

Activates the name management of a node. Not until the name management is activated another node can change the device name of this node by sending a name management message.

## Parameters

- **fs**: FS simulation node to apply the function
- **enable**:
  - 1: activate the name management
  - 0: deactivates the name management
- **bitmask**: Parts of the device name that are allowed to be changed:
  - bit 0 (LSB): Arbitrary Address Capable
  - bit 1: Industry Group
  - bit 2: System Instance
  - bit 3: System
  - bit 4: Function
  - bit 5: Function Instance
  - bit 6: ECU Instance
  - bit 7 (MSB): Manufacturer Code

## Return Values

0 on success or [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 2

```c
//allow every component to be changed except arbitrary address capable flag
FSIL_EnableNameManagement(1, 0xFE);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
