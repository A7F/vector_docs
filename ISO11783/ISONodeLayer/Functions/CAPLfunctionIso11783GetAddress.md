[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783GetAddress.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783GetAddress

# Iso11783GetAddress

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword Iso11783GetAddress( char[] busName, dword componentMask, char deviceName[8] );
dword Iso11783GetAddress( long busHandle, dword componentMask, char deviceName[8] );
```

## Description

This function returns a network address with which a device that is described by the function parameters logged onto the network.

## Parameters

- **busName**: Bus name or "default"
- **busHandle**: Bus handle, see [Iso11783GetBus](CAPLfunctionIso11783getbus.md)
- **componentMask**: The bitmask specifies the part of the name, which should be used for comparison. To compare the whole name use the value 0x1ff. Combine the values of the following table with "or" to compare only parts of the name. If there are more than one node which fits to name, only the first one is returned.

  - **1**: Self-configurable
  - **2**: Industry group
  - **4**: Device class instance
  - **8**: Device class
  - **16**: Function
  - **32**: Function instance
  - **64**: ECU instance
  - **128**: Manufacturer code
  - **256**: Identity number

- **deviceName**: Device name

## Return Values

Address of the node or Null Address (0xFE) if no device is found or FFFFFFFFh if the functions fails.

## Example

```plaintext
char deviceName[8] = { 0, 0, 0, 0, 0 ,0, 0, 0};
address = Iso11783GetAddress( "default", 0x1ff, deviceName);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
