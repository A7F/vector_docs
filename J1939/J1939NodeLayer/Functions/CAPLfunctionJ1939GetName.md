[J1939GetName](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939GetName.md)

**CAPL Functions** » **J1939** » **J1939 NL** » **J1939GetName**

# J1939GetName

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939GetName( char[] busName, dword componentMask, char deviceName[] );
dword J1939GetName( long busHandle, dword componentMask, char deviceName[] );
```

## Description

This function returns the name of a device that was logged onto the network with `address`. The function works with a global table that contains all node names and addresses logged onto the network.

If no device is logged onto the network with address #10 then `name`={8*DEFAULT_VALUE}. In this version DEFAULT_VALUE is 0.

## Parameters

- **busName**: bus name or "default"
- **busHandle**: bus handle, see [J1939GetBus](CAPLfunctionj1939getbus.md)
- **componentMask**: address of the node
- **deviceName**: buffer to which the data is copied (size: 8 Byte).

## Return Values

- **0**: ok
- **3**: unknown address

## Example

```plaintext
char deviceName[8];
J1939GetName( "default", 0, deviceName );
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
