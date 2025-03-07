[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPUDPSendPort.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_UDPSendPort

# DoIP_UDPSendPort

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### DoIP_UDPSendPort (raw)

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
long DoIP_UDPSendPort(char IPaddress[], word port, byte data[], dword length);
```

## Description

Send given raw data to peer(s) as UDP frame.

## Parameters

- **IPaddress**: Send to this address, may be a broadcast address.
- **port**: Destination port for the UDP packet.
- **data**: The UDP payload, i.e. it must contain a DoIP header if the peer shall recognize it as such.
- **length**: Payload length

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
// Send an invalid identification request to a non-standard port of a 
// specific vehicle that must ignore it
BYTE rawData[8] = { 0x02,0xFF /*wrong!*/, 0x00,0x01, 0x00,0x00,0x00,0x00};
DoIP_UDPSendPort( "169.254.123.45", 13401 /* non standard */, rawData, elcount( rawData));
```

## DoIP_UDPSendPort (PDU)

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
long DoIP_UDPSendPort(char IPaddress[], dword port, dword payloadType, byte payload[], dword payloadLen);
```

## Description

Sends a DoIP PDU with valid layout to peer(s) as UDP frame. The configured DoIP version is used.

## Parameters

- **IPaddress**: Send to this address, may be a broadcast address.
- **port**: Destination port for the UDP packet.
- **payloadType**: Type to send, i.e. this can be any value. [0; 0xFFFF]
- **payload**: The data following the generic DoIP header.
- **payloadLen**: Payload length.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
// Send an invalid identification request to a non-standard port of a 
// specific vehicle that must ignore it
BYTE rawData[8] = { 0x02,0xFF /*wrong!*/, 0x00,0x01, 0x00,0x00,0x00,0x00};
DoIP_UDPSendPort( "169.254.123.45", 13401 /* non standard */, rawData, elcount( rawData));
```

[DoIP_UDPSend](CAPLfunctionDoIPUDPSend.md) • [DoIP_TCPSend](CAPLfunctionDoIPTCPSend.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)