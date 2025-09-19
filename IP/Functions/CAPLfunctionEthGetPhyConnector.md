# ethGetPhyConnector

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthGetPhyConnector.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethGetPhyConnector**

## Function Syntax

```plaintext
byte ethGetPhyConnector(ethernetPort port, EthernetPhyConnector& phyConnector);
```

## Description

Gets the PHY connector.

Only supported for [network-based configurations](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) and **physical** measurement ports.

## Parameters

- **port**: Ethernet port.
- **phyConnector**:
  - 0: kEthernetPhyConnectorDefault (the only available connector on this channel)
  - 1: kEthernetPhyConnectorRJ45
  - 2: kEthernetPhyConnectorDSub

## Return Values

- **0**: Failure
- **1**: Success

## Example

```plaintext
void print()
{
  stack ethernetPort port = ethernetPort::Ethernet1::Port1;
  stack enum EthernetPhyConnector connector;

  if (ethGetPhyConnector(port, connector) != 0)
  {
    printConnector(connector);
  }
}

void printConnector(enum EthernetPhyConnector connector)
{
  char str[64];

  switch (connector)
  {
    case kEthernetPhyConnectorDefault:
      strncpy(str, "kEthernetPhyConnectorDefault", elcount(str));
      break;
    case kEthernetPhyConnectorRJ45:
      strncpy(str, "kEthernetPhyConnectorRJ45", elcount(str));
      break;
    case kEthernetPhyConnectorDSub:
      strncpy(str, "kEthernetPhyConnectorUnknown", elcount(str));
      break;
    default:
      write("error");
      return;
  }

  write("connector: %s", str);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
