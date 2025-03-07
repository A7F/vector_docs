[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetCAK.md)

## EthernetMacsecConfiguration::GetCAK

**CAPL Functions** » **Ethernet** » **Function Overview** » EthernetMacsecConfiguration::GetCAK

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Method Syntax

`dword EthernetMacsecConfiguration.GetCAK(byte cak[]);`

### Description

Copies the current connectivity association key (CAK) of the given MACsec configuration into the byte array given as parameter.

Note that if the EAP-TLS protocol is in use, the CAK and CKN will be determined from the result of the EAP-TLS handshake.

### Parameters

- **cak[]**: A buffer where to copy the CAK.

### Return Values

- **dword**: The number of bytes copied into the specified byte array.

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)