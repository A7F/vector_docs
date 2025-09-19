[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionOutputEthernet.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » output (Ethernet)

# output (Ethernet)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `void output(ethernetPacket packet); // form 1`
- `void output(ethernetPacket packet, dword fcs); // form 2`
- `void output(ethernetErrorPacket packet); // form 3`

## Description

Outputs an Ethernet packet (form 1) from the program block.  
Form 2 can be used to output Ethernet packets with an invalid frame checksum.

## Parameters

- **packet**: Variable of type [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md) (form 1 and 2) or [ethernetErrorPacket](../Objects/CAPLfunctionEthernetErrorPacket.md) (form 3).
- **fcs**: Ethernet packet check sequence.

## Return Values

—

## Example

```c
ethernetPacket txPacket;

txPacket.msgChannel = 1;
txPacket.source      = EthGetMacAddressAsNumber("20:00:00:00:00:01");
txPacket.destination = EthGetMacAddressAsNumber("FF:FF:FF:FF:FF:FF");
txPacket.Length = 100;
txPacket.type = 0xF123;

output(txPacket, 0x1234);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
