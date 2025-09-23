[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILEnableNameManagement.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_EnableNameManagement**

# TCIL_EnableNameManagement

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword TCIL_EnableNameManagement(dword enable); // form 1`
- `dword TCIL_EnableNameManagement(dword enable, dword bitMask); // form 2`
- `dword TCIL_EnableNameManagement(dbNode tc, dword enable); // form 3`
- `dword TCIL_EnableNameManagement(dbNode tc, dword enable, dword bitMask); // form 4`

## Description

This function activates the name management of a node. Not until the name management is activated another node can change the device name of this node by sending a name management message.

## Parameters

- **tc**: TC simulation node to apply the function
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
TCIL_EnableNameManagement(1, 0xFE);
```
