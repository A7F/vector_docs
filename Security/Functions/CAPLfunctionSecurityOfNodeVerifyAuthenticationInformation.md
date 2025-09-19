[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityOfNodeVerifyAuthenticationInformation.md)

# SecurityOfNodeVerifyAuthenticationInformation

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityOfNodeVerifyAuthenticationInformation

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

- `long SecurityOfNodeVerifyAuthenticationInformation(dword dataId, byte payload[], dword payloadLength, qword truncatedAuthenticatorHigh, qword truncatedAuthenticator, dword truncatedAuthenticatorBitLength, qword rxFreshness, dword rxFreshnessBitLength, qword currentFreshness, dword freshnessValueLength, dword freshnessValueId, dword verificationResult)` // form 1
- `long SecurityOfNodeVerifyAuthenticationInformation(dword dataId, byte payload[], dword payloadLength, qword truncatedAuthenticatorHigh, qword truncatedAuthenticator, dword truncatedAuthenticatorBitLength, qword rxFreshness, dword rxFreshnessBitLength, qword currentFreshness, dword freshnessValueLength, dword freshnessValueId, dword keyId, dword verificationResult)` // form 2

## Description

Verifies the specified authentication information (MAC and freshness) of the PDU. The (complete) current freshness value must be provided in the function call. Other freshness sources will be ignored. The payload is also an input parameter to the verification logic.

The result of this method depends on the security profile which is mapped on the network.

You have to call [SecurityLocalStartControlSimulationNode](CAPLfunctionSecurityLocalStartControlSimulationNode.md) before this callback is called.

## Parameters

- **char nodeName[]**: The name of the node.
- **char networkName[]**: The name of the network the node is on.
- **dword dataId**: The data ID of the PDU to lookup the desired key in the security source.
- **byte payload[]**: The payload of the PDU.
- **dword payloadLength**: The payload length of the PDU in bytes.
- **qword truncatedAuthenticatorHigh**: Upper 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits. Otherwise 0;
- **qword truncatedAuthenticator**: The full authenticator value or the lower 64 bits of the authenticator (MAC), if authenticator is larger than 64 bits.
- **dword truncatedAuthenticatorBitLength**: Length of complete authenticator to transmit (length of authInfo if the authenticator is <= 64 bit, otherwise length of authInfo + authInfoHigh)
- **qword rxFreshness**: The received freshness value.
- **dword rxFreshnessBitLength**: The length of the received (typically truncated) freshness in bits.
- **qword currentFreshness**: The freshness value to be used for calculation.
- **dword freshnessValueBitLength**: The length of currentFreshness in bits.
- **dword freshnessValueId**: The freshness value ID of the PDU.
- **dword keyId**: The ID used to identify the key for verification of the authenticator, if the key is not identified by the data ID.
- **dword verificationResult [Out]**:
  - 1: Valid MAC
  - 0: Invalid MAC

## Return Values

A Value of 1 means that the action was successful. A value less than or equal to 0 means error.

- **1**: Success.
- **0**: Error, no details.
- **-1**: Invalid handle.
- **-2**: Data incomplete.
- **-3**: Signal length does not fit.
- **-4**: Security source error, no details.
- **-6**: Not supported.
- **-10**: Security is not usable. Reasons can be: Security Manager version is too old. Tool Version is too old. Security Profile is invalid.

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
