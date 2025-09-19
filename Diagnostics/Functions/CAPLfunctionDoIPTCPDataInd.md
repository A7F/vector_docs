# _DoIP_TCPDataInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void _DoIP_TCPDataInd( BYTE DoIPVersion, WORD payloadType, BYTE payload[]);
```

## Description

A DoIP PDU was received from the connected peer that cannot be interpreted by this implementation.

## Parameters

- **DoIPVersion**: Protocol version as sent in the header.
- **payloadType**: Value from the header.
- **payload**: The payload.

## Return Values

—

## Example

```plaintext
void _DoIP_TCPDataInd( BYTE DoIPVersion, WORD payloadType, BYTE payload[])
{
  write( "_DoIP_TCPDataInd( version=%d, type %04x, [%d]<%02x...>)"
  , DoIPVersion, payloadType
  , elcount( payload), elcount(payload) > 0 ? payload[0] : 0);
}
```

[DoIP_TCPSend](CAPLfunctionDoIPTCPSend.md)
