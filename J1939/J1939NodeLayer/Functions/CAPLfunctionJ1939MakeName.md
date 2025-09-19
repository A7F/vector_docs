[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939MakeName.md)

**CAPL Functions** » **J1939** » **J1939 NL** » **J1939MakeName**

# J1939MakeName

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
void J1939MakeName( char[] retDeviceName, long selfConfiguring, long industryGroup, long deviceClassInstance, long deviceClass, long function, long functionInstance, long ECUInstance, long manufacturerCode, long identityNumber );
```

## Description

This function creates a J1939 device name.

The parameter `retDeviceName` must be an array with size 8. It will be filled with the device name.

## Parameters

- **retDeviceName**: device name is copied in this buffer (must be 8 bytes)

## Return Values

—

## Example

```plaintext
char name[8];
J1939MakeName( name, 1, 2, 3, 4, 5, 6, 7, 8, 9);
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
