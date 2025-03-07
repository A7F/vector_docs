[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPTCPSend.md)

# DoIP_TCPSend

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_TCPSend

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
long DoIP_TCPSend(dword payloadType, byte payload[], dword payloadLen);
long DoIP_TCPSend(dword protocolID, dword payloadType, byte payload[], dword payloadLen);
```

## Description

Sends a DoIP PDU with valid layout on the open TCP connection.

## Parameters

- **protocolD**: If given, this will replace the configured protocol version in the DoIP PDU. [0; 255]
- **payloadType**: Type to send, i.e. this can be any value. [0; 0xFFFF]
- **payload**: The data following the generic DoIP header.
- **payloadLen**: Length of the data following the header.

## Return Values

Error code, e.g. connection not established yet.

## Example

```plaintext
// When a vehicle is connected, send a non-standard frame to the peer
On key '1'
{
  BYTE payload[3] = { 0x11, 0x22, 0x33 };
  // the frame type 0xF222 is manufacturer-specific
  DoIP_TCPSend( 0xF222, payload, elcount( payload));
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)