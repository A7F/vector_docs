# _DoIP_UDPPreSend

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
long _DoIP_UDPPreSend( BYTE DoIPVersion[], BYTE inverseVersion[], WORD payloadType[], DWORD payloadLen[], BYTE payload[]);
```

## Description

The DoIP implementation is about to send an UDP DoIP packet with the given content. It is possible to change the values in header and data, and to change the total length of the UDP packet.

**Note**  
Note that packets sent by DoIP_UDPSend are NOT indicated here since it is possible to provide any data using these calls anyway.

## Parameters

- **DoIPVersion**: Protocol version value to send, defaults to configured value.
- **inverseVersion**: Inverse protocol version value to send.
- **payloadType**: Type of the PDU sent. The value is converted from and to network byte order automatically.
- **payloadLen**: Length of the payload as indicated in the header. The value is converted from and to network byte order automatically.
- **payload**: Payload itself. [Elcount(payload)](../../Other/Functions/CAPLfunctionElCount.md) indicates the maximum number of bytes that can be accessed in the callback which might be longer than **payloadLen**, i.e. more bytes might be available than used for DoIP.

## Return Values

- **-1**: Drop this UDP packet, i.e. it is NOT sent. This may cause errors in the protocol state machine.
- **0**: The total length of the UDP packet is computed from the payload length value.
- **> 0**: Send a UDP packet with this length. For example, values < 8 will cut the DoIP header, i.e. the announced payload is not actually sent.
- **Others**: Reserved

## Example

```plaintext
// Patch the UDP packet send depending on a global control variable
long _DoIP_UDPPreSend( BYTE DoIPVersion[], BYTE inverseVersion[], WORD payloadType[], DWORD payloadLen[], BYTE payload[])
{
  long retVal;
  write( "UDPPreSend( version=%02x, invVersion=%02x, payloadtype=%04x, payloadLen=%d, [%d]<%02x ...>)"
  , DoIPVersion[0], inverseVersion[0], payloadType[0], payloadLen[0], elcount( payload)
  , elcount( payload) > 0 ? payload[0] : 0);
  retVal = 0;
  switch( sNextUDPFault)
  {
    case 1: // increase payload by 2 bytes and patch type to force a UDP response
      payload[payloadLen[0]] = 0xFF;
      payload[payloadLen[0] + 1] = 0xFF;
      payloadLen[0] += 2;       // increase payload length!
      payloadType[0] += 0x200;  // patch type
      break;

    case 2: // increase packet length
      retVal = 1000;
      break;

    case 3: // drop packet
      retVal = -1;
      break;
    default:
      return 0;
  }
  sNextUDPFault = 0;
  return retVal;
}
```

[DoIP_UDPSend](CAPLfunctionDoIPUDPSend.md)
