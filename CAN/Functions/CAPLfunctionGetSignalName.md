[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionGetSignalName.md)

**CAPL Functions** » **CAN** » **getSignalName**

# getSignalName

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
char[] getSignalName(caplCanMessage* msg, dword startBit); // form 1
char[] getSignalName(caplAutosarPDU* pdu, dword startBit); // form 2
```

## Description

Finds out the signal name at a specified start index inside a CAN message (form 1).

Finds out the signal name at a specified start index inside a PDU (form 2).

## Parameters

- **msg**: CAN message.
- **pdu**: AUTOSAR PDU.
- **startBit**: First bit of the signal of the AUTOSAR PDU or CAN message.

## Return Values

Returns the signal name at a given start index inside a CAN message. Start index is defined in DBC Editor (form 1).

Returns signal name at a given start index inside a PDU. Start index is defined with AUTOSAR Explorer (form 2).

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)