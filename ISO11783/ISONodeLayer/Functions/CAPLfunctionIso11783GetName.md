# Iso11783GetName

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword Iso11783GetName( char[] busName, dword componentMask, char deviceName[] );
dword Iso11783GetName( long busHandle, dword componentMask, char deviceName[] );
```

## Description

This function returns the name of a device that was logged onto the network with `address`. The function works with a global table that contains all node names and addresses logged onto the network.

If no device is logged onto the network with address #10 then `name`={8*DEFAULT_VALUE}. In this version DEFAULT_VALUE is 0.

## Parameters

- **busName**: Bus name or "default"
- **busHandle**: Bus handle, see [Iso11783GetBus](CAPLfunctionIso11783getbus.md)
- **componentMask**: Address of the node
- **deviceName**: Buffer to which the data is copied (size: 8 Byte).

## Return Values

0 - success or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
char deviceName[8];
Iso11783GetName( "default", 0, deviceName );
```
