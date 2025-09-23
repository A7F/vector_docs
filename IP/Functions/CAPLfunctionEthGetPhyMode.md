[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthGetPhyMode.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethGetPhyMode

# ethGetPhyMode

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
byte ethGetPhyMode(ethernetPort port, EthernetPhyMode& phyMode);
```

## Description

Gets the PHY mode.

Only supported for [network-based configurations](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) and **physical** measurement ports.

## Parameters

- **port**: Ethernet port.
- **phyMode**:
  - 0: kEthernetPhyModeUnknown
  - 1: kEthernetPhyModeMaster
  - 2: kEthernetPhyModeSlave

## Return Values

- **0**: Failure
- **1**: Success

## Example

```plaintext
void print()
{
  stack ethernetPort port = ethernetPort::Ethernet1::Port1;
  stack enum EthernetPhyMode mode;

  if (ethGetPhyMode(port, mode) != 0)
  {
    printMode(mode);
  }
}

void printMode(enum EthernetPhyMode mode)
{
  char str[64];

  switch(mode)
  {
    case kEthernetPhyModeUnknown:
      strncpy(str, "kEthernetPhyModeUnknown", elcount(str));
      break;
    case kEthernetPhyModeMaster:
      strncpy(str, "kEthernetPhyModeMaster", elcount(str));
      break;
    case kEthernetPhyModeSlave:
      strncpy(str, "kEthernetPhyModeSlave", elcount(str));
      break;
    default:
      write("error");
      return;
  }

  write("mode: %s", str);
}
```
