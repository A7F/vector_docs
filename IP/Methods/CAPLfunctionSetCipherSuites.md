[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetCipherSuites.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **EthernetMacsecConfiguration::SetCipherSuites**

# EthernetMacsecConfiguration::SetCipherSuites

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

`dword EthernetMacsecConfiguration.SetCipherSuites(qword cs[], dword length);`

## Description

Sets the cipher suite priority list of the MACsec configuration from the given qword array.

When MKA is running, the list of configured ciphers suites will be distributed using announcement parameter sets included in the MKPDU, provided transmission of announcements hasn’t been deactivated in the MACsec configuration. The designated MKA key server will go through its own cipher suite id list and search for a common cipher suite between himself and its peer. The first found cipher suite will then be used.

The key client will basically do the same: he will go through the cipher suite id list provided by the key server, and try to find a matching cipher suite in his own configured cipher suite id list.

If announcements are deactivated, both participants should have the same, single cipher suite id configured in this list.

## Parameters

- **cs[]**: A qword array from where to copy the cipher suite ids.
- **length**: The number of bytes to copy from the byte array. Note that a CKN must be 1 byte minimum, 32 bytes maximum.

## Return Values

- **dword**: The number of qwords, representing cipher suite ids, copied from the specified qword array.

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
