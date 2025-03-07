[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionFaultInjectDisableLengthPadding.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethernetPacket::FaultInjectDisableLengthPadding**

# ethernetPacket::FaultInjectDisableLengthPadding

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

dword [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md).FaultInjectDisableLengthPadding();

## Description

Disable automatic padding of Ethernet data to minimal length. Use this to send Ethernet packet, which are smaller than 64 byte (including FCS). The smallest length that can be sent is 24 byte (Ethernet header with FCS).

**Note:** Only supported with Vector Ethernet network interfaces.

## Parameters

—

## Return Values

- **0**: success

## Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)