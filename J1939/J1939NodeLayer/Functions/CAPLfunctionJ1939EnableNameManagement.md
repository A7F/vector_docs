[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939EnableNameManagement.md)

**CAPL Functions** » **J1939** » **J1939 NL** » **J1939EnableNameManagement**

# J1939EnableNameManagement

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939EnableNameManagement( dword ecuHandle, dword enable )
dword J1939EnableNameManagement( dword ecuHandle, dword enable, dword bitMask )
```

## Description

This function activates the name management of a node. Not until the name management is activated another node can change the device name of this node by sending a name management message.

## Parameters

- **ecuHandle**: ECU handle
- **enable**:
  - 1: activate the name management
  - 0: deactivates the name management
- **bitMask**: parts of the device name that are allowed to be changed
  - bit 0 (LSB): Arbitrary Address Capable
  - bit 1: Industry Group
  - bit 2: System Instance
  - bit 3: System
  - bit 4: Function
  - bit 5: Function Instance
  - bit 6: ECU Instance
  - bit 7 (MSB): Manufacturer Code

## Return Values

0 or [error code](../CAPLfunctionsJ1939NLErrorCodes.md)

## Example

```plaintext
LONG busHandle;
LONG ecuAddress;
LONG ecuHandle;
char deviceName[8]; // device name of the node

busHandle  = J1939GetBus( "J1939" );
ecuAddress = dbNode.NmStationAddress; // dbNode must be configured in database

J1939MakeName(
  deviceName, dbNode.NmJ1939AAC,
  dbNode.NmJ1939IndustryGroup,
  dbNode.NmJ1939SystemInstance,
  dbNode.NmJ1939System,
  dbNode.NmJ1939Function,
  dbNode.NmJ1939FunctionInstance,
  dbNode.NmJ1939ECUInstance,
  dbNode.NmJ1939ManufacturerCode,
  dbNode.NmJ1939IdentityNumber
);
ecuHandle = J1939CreateECU( busHandle, deviceName );

if (ecuHandle != 0)
{
  /* allow every component to be changed except arbitrary address capable flag */
  J1939EnableNameManagement(ecuHandle, 1, 0xFE);
  J1939ECUGoOnline( ecuHandle, ecuAddress );
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
