[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetCKN.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **EthernetMacsecConfiguration::SetCKN**

# EthernetMacsecConfiguration::SetCKN

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

`dword EthernetMacsecConfiguration.SetCKN(byte cak[], dword length);`

## Description

Sets the current connectivity key name (CKN) of the MACsec configuration from the given byte array. Note that a CKN is limited to 32 bytes maximum.

## Parameters

- **cak[]**: A buffer from where to copy the CKN.
- **length**: The number of bytes to copy from the byte array. Note that a CKN must be 1 byte minimum, 32 bytes maximum.

## Return Values

- **dword**: The number of bytes copied into the specified byte array.

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)