[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbOpenListener.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [AVB IL](../CAPLfunctionsAVBILOverview.md) » AvbOpenListener

# AvbOpenListener

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword AvbOpenListener(); // form 1`
- `dword AvbOpenListener(dword streamUniqueId); // form 2`
- `dword AvbOpenListener(byte streamSourceAddress[]); // form 3`
- `dword AvbOpenListener(byte streamSourceAddress[], dword streamUniqueId); // form 4`

## Description

The function creates a Listener for use in connection-based, message-oriented communications.

## Parameters

- **streamUniqueId**: The stream’s unique identifier.
- **streamSourceAddress**: The stream’s source MAC address (48 bit).

## Return Values

- **0**: The function failed. Call [AvbGetLastError](CAPLfunctionAvbGetLastError.md) to get a more specific error code.
- **Any other value**: A valid Listener handle identifying the created Listener.

## Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
