[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILEnableNameManagement.md)

**CAPL Functions » ISO11783 » Virtual Terminal Interaction Layer (VT IL) » VTIL_EnableNameManagement**

# VTIL_EnableNameManagement

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
dword VTIL_EnableNameManagement(dword enable);
dword VTIL_EnableNameManagement(dword enable, dword bitMask);
```

## Description

This function activates the name management of a node. Not until the name management is activated another node can change the device name of this node by sending a name management message.

## Parameters

- **enable**
  - 1: activate the name management
  - 0: deactivates the name management

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

## Return Values

0 on success or [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
//allow every component to be changed except arbitrary address capable flag
VTIL_EnableNameManagement(1, 0xFE);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
