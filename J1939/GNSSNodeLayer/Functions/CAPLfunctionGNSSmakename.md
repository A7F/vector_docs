[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSmakename.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSMakeName

# GNSSMakeName

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void GNSSMakeName( word deviceName[8], dword selfConfigurable, dword industryGroup, dword deviceClassInstance, dword deviceClass, dword function, dword functionInstance, dword ECUInstance, dword manufacturerCode, dword identityNumber);
```

## Description

The function generates a J1939 device name. It must be transferred with a byte array of size 8. This array is filled with the device name.

## Parameters

- **deviceName**: Name of the device (determines the function)
- **selfConfigurable**: Self-configurability of the device
- **industryGroup**: Industry group
- **deviceClassInstance**: Instance of a device class on the network
- **deviceClass**: Device class
- **function**: Function
- **functionInstance**: Instance of a function on the network
- **ECUInstance**: An ECU instance
- **manufacturerCode**: Manufacturer of the device
- **identityNumber**: Manufacturer-specific number

## Return Values

—

## Example

```plaintext
char name[8];
GNSSMakeName(name, 1, 0, 0, 0, 28, 0, 0, 0, 0);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)