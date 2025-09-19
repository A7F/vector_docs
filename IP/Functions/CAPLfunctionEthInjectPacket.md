[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthInjectPacket.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethInjectPacket

# ethInjectPacket

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ethInjectPacket (ethernetPacket packet, byte direction);
```

## Description

Transmits an Ethernet packet by a specific **ethernetPort** defined in `<packet>`. Allows to output a frame not only on a simulation port like [output](CAPLfunctionOutputEthernet.md), but on a physical port as well e.g. for error injection.

**Note:** The injection is not supported for measurement ports that are connected to a multidrop segment in the hardware configuration.

## Parameters

- **packet**: Variable of type **ethernetPacket**.
- **direction**: Transmit direction from viewpoint of the connected segment:
  - `<rx>` or `<0>` to send from a simulated port (into the connected segment) in real mode
  - `<tx>` or `<1>` to send from a physical measurement port (away from the connected segment) in real mode
  - In simulated mode use `<tx>` or `<rx>` (respectively `<0>` or `<1>`) to send from simulated ports either into the connected segment (rx) or away from the connected segment (tx).

## Return Values

- **0**: Success
- **1**: Invalid Ethernet port
- **2**: Packet failure
- **3**: Output not allowed

## Example

```plaintext
ethernetPacket txPacket;

txPacket.hwPort = ethernetPort::Ethernet1::Port1;
txPacket.source = EthGetMacAddressAsNumber("20:00:00:00:00:01");
txPacket.destination = EthGetMacAddressAsNumber("FF:FF:FF:FF:FF:FF");
txPacket.Length = 100;
txPacket.type = 0xF123;

ethInjectPacket(txPacket, tx);  // send over physical port <Port1> of network <Ethernet1>
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
