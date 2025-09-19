# _DoIP_UDPInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```
long _DoIP_UDPInd( char IPaddress[], WORD port, BYTE data[]);
```

## Description

An UDP packet was received. All packets are forwarded to this callback function, and it can decide whether processing of the packet stops, or is continued. The sender IP address and source port is given as first arguments.

**Note**  
This callback is called for every packet before any other processing is performed. If only packets unknown to the DoIP implementation shall be processed, use [_DoIP_UDPDataInd](CAPLfunctionDoIPUDPDataInd.md).

## Parameters

- **IPaddress**: Address in text form, e.g. "169.254.32.1" (IPv4) or "2001::1" (IPv6).
- **port**: IP source port of the packet at the sender.
- **data**: The raw data received, including complete header, if present.

## Return Values

- **0**: Continue normal processing of the packet.
- **-1**: Ignore the packet, i.e. all processing stops other reserved.

## Example

```c
// If packet with payload type 0xF000 is received, answer with a 0xF001 packet
// and stop processing. Otherwise process the packet normally.
long _DoIP_UDPInd( char IPaddress[], WORD port, BYTE data[])
{
  WORD payloadType;
  BYTE response[2] = { 0x12, 0x34 };
  if( elcount(data) < 8)
    return 0;
  payloadType = (data[2] << 8) + data[3];
  if( payloadType != 0xF000)
    return 0;

  DoIP_UDPSendPort( IPaddress, port, 0xF001, response, elcount( response));
  return -1; // we process this frame
}
```

[_DoIP_UDPDataInd](CAPLfunctionDoIPUDPDataInd.md) • [DoIP_UDPSend](CAPLfunctionDoIPUDPSend.md) • [DoIP_UDPSendPort](CAPLfunctionDoIPUDPSendPort.md)
