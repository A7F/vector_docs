[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783MakeName.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783MakeName

# Iso11783MakeName

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783MakeName( char[] retDeviceName, long selfConfiguring, long industryGroup, long deviceClassInstance, long deviceClass, long function, long functionInstance, long ECUInstance, long manufacturerCode, long identityNumber );
```

## Description

This function creates a Iso11783 device name.

The parameter `retDeviceName` must be an array with size 8. It will be filled with the device name.

## Parameters

- **retDeviceName**: Device name is copied in this buffer (must be 8 bytes)

## Return Values

—

## Example

```c
char name[8];
Iso11783MakeName( name, 1, 2, 3, 4, 5, 6, 7, 8, 9);
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
