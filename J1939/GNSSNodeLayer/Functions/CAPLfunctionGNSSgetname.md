[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSgetname.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSGetName**

# GNSSGetName

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSGetName( dword addr, byte name[] );
```

## Description

The function returns the J1939 device name of a control device that was logged on to the network with **addr**. The function works with a global table containing all node names and addresses logged on to the network.

## Parameters

- **addr**: Address of the device
- **name**: Name of the device

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
char name[8];
GNSSGetName( 10, name );
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
