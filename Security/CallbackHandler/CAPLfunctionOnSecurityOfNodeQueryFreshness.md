[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/CallbackHandler/CAPLfunctionOnSecurityOfNodeQueryFreshness.md)

## OnSecurityOfNodeQueryFreshness

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » OnSecurityOfNodeQueryFreshness

**Valid for:** CANoe DE • CANoe4SW DE

### Function Syntax

```
long OnSecurityOfNodeQueryFreshness(char nodeName[], char nameName[], dword context, char pduName[], dword dataId, dword freshnessValueId, dword attemptNr, byte payload[], dword payloadLength, qword& freshness, dword& freshnessLength, qword truncatedRxFreshness, dword truncatedRxFreshnessBitLength)
```

### Description

This callback is called for every secured PDU of the specified node on the specified network for which a MAC has to be calculated or verified. The callback is triggered before the MAC calculation starts. The callback provides the possibility to calculate a freshness value in CAPL and force the Security Manager to use this freshness value for the next MAC calculation/verification. You have to call [SecurityLocalStartControlSimulationNode](../Functions/CAPLfunctionSecurityLocalStartControlSimulationNode.md) before this callback is called.

### Parameters

- **char nodeName[]**: The name of the node.
- **char networkName[]**: The name of the network the node is on.
- **dword context**:
  - 1: PDU is received (MAC verification)
  - 0: PDU is transmitted (MAC calculation)
- **char pduName[]**: The name of the PDU.
- **dword dataId**: The data ID of the PDU.
- **dword freshnessValueId**: The freshness value ID of the PDU.
- **dword attemptNr**: The number of the attempted verification.
- **byte payload[]**: The payload of the PDU.
- **dword payloadLength**: The payload length of the PDU in bytes.
- **qword& freshness [Out]**: The freshness the CAPL code provides.
- **dword& freshnessLength [Out]**: The freshness length of the freshness the CAPL code provides in bits.
- **qword truncatedRxFreshness**: The received freshness (only in case context is 1).
- **dword truncatedRxFreshnessBitLength**: The received freshness length in bits (only in case context is 1).

### Return Values

- **qword& freshness [Out]**: The freshness the CAPL code provides.
- **dword& freshnessLength [Out]**: The freshness length of the freshness the CAPL code provides in bits.

- 0: No freshness is provided by this callback.
- 1: The freshness and freshnessLength shall be used for MAC calculation/verification.

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
