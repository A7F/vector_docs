[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/CallbackHandler/CAPLfunctionOnSecurityLocalPDUPreTx.md)

## CAPL Functions » Security » OnSecurityLocalPDUPreTx

### OnSecurityLocalPDUPreTx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note:** Replaces OnLocalSecurityPDUPreTx.

### Function Syntax

```c
void OnSecurityLocalPDUPreTx(char pduName[], dword dataId, byte payload[], dword payloadLength, qword& authInfoHigh, qword& authInfo, dword authInfoBitLength, qword& freshness, dword freshnessBitLength, dword freshnessValueId)
```

### Description

This callback handler is called after all data updates and the automatic Authenticator (MAC) calculation has been done. Payload, AuthInfo, and freshness can be modified in this handler before the transmission starts. Fault injection and evaluation of new algorithms are typical examples.

### Parameters

- **char pduName[]**: The name of the PDU.
- **dword dataId**: The data ID of the PDU.
- **byte payload[]**: The payload of the PDU.
- **dword payloadLength**: The payload length of the PDU in bytes.
- **qword& authInfoHigh [Out]**: Upper 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits. Otherwise 0.
- **qword& authInfo [Out]**: The full authenticator value or the lower 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits.
- **dword authInfoBitLength**: Length of complete authenticator to transmit (length of authInfo if the authenticator is \<= 64 bit, otherwise length of authInfo + authInfoHigh).
- **qword& freshness [Out]**: The transmitted freshness value.
- **dword freshnessBitLength**: The transmitted freshness value length in bits.
- **dword freshnessValueId**: The freshness value ID of the PDU.

### Return Values

- **byte payload[]**: The payload of the PDU.
- **qword& authInfoHigh [Out]**: Upper 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits. Otherwise 0.
- **qword& authInfo [Out]**: The full authenticator value or the lower 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits.
- **qword& freshness [Out]**: The freshness value.

### Example

```plaintext
// this example modifies the MAC of PDU with Data ID 1
void OnSecurityLocalPDUPreTx(char pduName[], dword dataId, byte payload[], dword payloadLength, qword& authInfoHigh, qword& authInfo, dword authInfoBitLength, qword& freshness, dword freshnessBitLength, dword freshnessValueId)
{
  if (dataId == 1)
  {
    authInfo = 0x123456; // change mac
    // freshness = 0x02; // change freshness
    // payload[0] = 0xFF; // change payload;
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
