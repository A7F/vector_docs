[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPTCPPreSend.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » _DoIP_TCPPreSend

# _DoIP_TCPPreSend

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
long _DoIP_TCPPreSend( BYTE DoIPVersion[], WORD payloadType[], DWORD payloadLen[], BYTE payload[]);
```

## Description

The DoIP implementation is about to send a TCP DoIP PDU with the given content. It is possible to change the values in header and data, to drop the PDU, and to reduce the length of the payload. Only DoIP PDUs with valid layout are sent.

**Note**  

- PDUs sent with DoIP_TCPSend are NOT indicated here since it is possible to provide any data using that call anyway.
- If the length of the PDU shall be increased, it is necessary to drop this PDU by returning -1, and send a longer PDU with [DoIP_TCPSend](CAPLfunctionDoIPTCPSend.md) later.

## Parameters

- **DoIPVersion**: Protocol version value to send, defaults to configured value.
- **payloadType**: Type of the PDU sent. The value is converted from and to network byte order automatically.
- **payloadLen**: Length of the payload as indicated in the header and actually sent. The value is converted from and to network byte order automatically.
- **payload**: Payload itself. [Elcount( payload)](../../Other/Functions/CAPLfunctionElCount.md) indicates the maximum number of bytes that can be accessed in the callback, and the maximum value **payloadLen** can be set to.

## Return Values

- **-1**: Drop this PDU. This might violate the DoIP protocol.
- **0**: Send the PDU with the data given.
- **Others**: Reserved

## Example

```plaintext
long _DoIP_TCPPreSend( BYTE DoIPVersion[], WORD payloadType[], DWORD payloadLen[], BYTE payload[])
{
  long retVal;
  write( "TCPPreSend( version=%02x, payloadtype=%04x, payloadLen=%d, [%d]<%02x ...>)"
  , DoIPVersion[0], payloadType[0], payloadLen[0], elcount( payload)
  , elcount( payload) > 0 ? payload[0] : 0);
  retVal = 0;
  switch( sNextTCPFault)
  {
    case 1: // Cut off 1 byte of data, if present
    if( payloadLen[0] > 0)
    {
      --payloadLen[0];
    }
    break;
    case 2: // patch payload type and DoIP version
    DoIPVersion[0] = 0x7;
    payloadType[0] += 0x100;
    break;
    case 3: // drop packet
    retVal = -1;
    break;
    default:
    return 0;
  }
  sNextTCPFault = 0;
  return retVal;
}
```

[DoIP_TCPSend](CAPLfunctionDoIPTCPSend.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)