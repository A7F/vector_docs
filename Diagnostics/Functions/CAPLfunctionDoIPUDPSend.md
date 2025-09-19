# DoIP_UDPSend

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## DoIP_UDPSend (raw)

### Note
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

### Function Syntax
```plaintext
long DoIP_UDPSend(byte data[], dword length);
long DoIP_UDPSend(char IPaddress[], byte data[], dword length);
```

### Description
Sends given raw data to peer(s) as UDP frame.

### Parameters
- **IPaddress**: If given, do not send to the selected peer, but to this address.
- **data**: The UDP payload, i.e. it must contain a DoIP header if the peer shall recognize it as such.
- **length**: Payload length.

### Return Values
[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

### Example
```plaintext
// Send an invalid identification request to a specific vehicle
// that must ignore it
BYTE rawData[8] = { 0x02,0xFF /* wrong! */, 0x00,0x01, 0x00,0x00,0x00,0x00};
DoIP_UDPSend( "169.254.123.45", rawData, elcount( rawData));
```

## DoIP_UDPSend (PDU)

### Function Syntax
```plaintext
long DoIP_UDPSend(dword payloadType, byte payload[], dword payloadLen);
long DoIP_UDPSend(char IPaddress[], dword payloadType, byte payload[], dword payloadLen);
```

### Description
Sends a DoIP PDU with valid layout to peer(s) as UDP frame. The configured DoIP version is used.

### Parameters
- **IPaddress**: If given, do not send to the selected peer, but to this address.
- **payloadType**: Type to send, i.e. this can be any value. [0; 0xFFFF]
- **payload**: The data following the generic DoIP header.
- **payloadLen**: Payload length.

### Return Values
[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

### Example
```plaintext
// Send a DoIP PDU with valid layout but non-standard type
// to a specific vehicle
BYTE payload[3] = { 0x12, 0x34, 0x45};
DoIP_UDPSend( "169.254.123.45", 0xF333, payload, elcount( payload));
```

[DoIP_TCPSend](CAPLfunctionDoIPTCPSend.md) • [DoIP_UDPSendPort](CAPLfunctionDoIPUDPSendPort.md)
