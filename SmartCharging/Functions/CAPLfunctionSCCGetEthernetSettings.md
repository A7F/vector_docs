[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetEthernetSettings.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [General Functions](../CAPLFunctionsSmartChargingOverview.md#GeneralFunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#GeneralFunctions) » **SCC_GetEthernetSettings**

# SCC_GetEthernetSettings

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_GetEthernetSettings(byte MacAddress[], byte IPv4Address[], dword& IPv4Available, byte IPv6Address[], dword& IPv6Available, dword& UDPPort, dword& TCPPort)
```

## Description

Gets the configured addresses and ports for the SCC node. These values may originate from the CANoe DE product configuration or from the DLL’s XML configuration.

## Parameters

- **MacAddress**: Queries the 6 byte MAC address (to the given byte buffer).
- **IPv4Address**: Queries the 4 byte IPv4 address (to the given byte buffer).
- **IPv4Available**: Gets 1 if IPv4Address is valid, else 0 (via reference).
- **IPv6Address**: Queries the 16 byte IPv6 address (to the given byte buffer).
- **IPv6Available**: Gets 1 if IPv6Address is valid, else 0 (via reference).
- **UDPPort**: Gets the UDP port number for SECC Discovery (via reference).
- **TCPPort**: Gets the TCP port number for Vehicle2Grid TP (via reference).

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
