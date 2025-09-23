[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalCalculateAuthenticator.md)

## SecurityLocalCalculateAuthenticator

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalCalculateAuthenticator

**Valid for**: CANoe DE • CANoe4SW DE

### Note

Replaces `LocalSecurityCalculateAuthenticator`.

### Function Syntax

```c
long SecurityLocalCalculateAuthenticator(dword dataId, byte payload[], dword payloadLength, qword truncatedAuthenticatorHigh, qword truncatedAuthenticator, dword truncatedAuthenticatorBitLength, qword freshness, dword truncatedFreshnessBitLength, dword freshnessValueBitLength, dword freshnessValueId) // form 1
```

```c
long SecurityLocalCalculateAuthenticator(dword dataId, byte payload[], dword payloadLength, qword truncatedAuthenticatorHigh, qword truncatedAuthenticator, dword truncatedAuthenticatorBitLength, qword freshness, dword truncatedFreshnessBitLength, dword freshnessValueBitLength, dword freshnessValueId, dword keyId) // form 2
```

### Description

Calculate the authenticator from arbitrary data. The (complete) freshness value must be provided in the function call. Other freshness sources will be ignored. The method returns the truncated freshness via **freshness** parameter. The calculated authenticator is returned via the **TruncatedAuthenticator** parameter. The truncated bit lengths of the authenticator and freshness can be modified.

The result of this method depends on the security profile which is mapped on the network.

### Parameters

- **dword DATAID**: The data ID of the PDU to lookup the desired key in the security source.
- **byte payload[]**: The payload of the PDU.
- **dword payloadLength**: The payload length of the PDU in bytes.
- **qword truncatedAuthenticatorHigh [Out]**: Upper 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits. Otherwise 0;
- **qword truncatedAuthenticator [Out]**: The full authenticator value or the lower 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits.
- **dword truncatedAuthenticatorBitLength [In/Out]**: Length of complete authenticator to transmit (length of authInfo if the authenticator is `<= 64` bit, otherwise length of authInfo + authInfoHigh).
- **qword freshness [In/Out]**:
  - In: The full freshness value for MAC calculation.
- **dword truncatedFreshnessBitLength [In/Out]**: The length of the truncated freshness in bits.
- **dword freshnessValueBitLength**: The freshness value length in bits.
- **dword freshnessValueId**: The freshness value ID of the PDU.
- **dword keyId**: The ID used to identify the key for calculating the authenticator, if the key is not identified by the data ID.

### Return Values

- **qword truncatedAuthenticatorHigh [Out]**: Upper 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits. Otherwise 0;
- **qword truncatedAuthenticator [Out]**: The full authenticator value or the lower 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits.
- **dword truncatedAuthenticatorBitLength [In/Out]**: Length of complete authenticator to transmit (length of authInfo if the authenticator is `<= 64` bit, otherwise length of authInfo + authInfoHigh).
- **qword freshness [In/Out]**: In: The full freshness value for MAC calculation. Out: Truncated tx freshness.
- **dword truncatedFreshnessBitLength [In/Out]**: The length of the truncated freshness in bits.

A Value of 1 means that the action was successful. A value less than or equal to 0 means error.

- **1**: Success
- **0**: Error, no details
- **-1**: Invalid handle
- **-2**: Data incomplete
- **-3**: Signal length does not fit
- **-4**: Security source error, no details
- **-6**: Not supported
- **-10**: Security is not usable. Reasons can be: Security Manager version is too old. Tool Version is too old. Security Profile is invalid.

### Example

—
