[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthGetPhyMedium.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethGetPhyMedium**

# ethGetPhyMedium

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
byte ethGetPhyMedium(ethernetPort port, EthernetPhyMedium& phyMedium);
```

## Description

Gets the PHY medium.

Only supported for [network-based configurations](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) and **physical** measurement ports.

## Parameters

- **port**: Ethernet port.
- **phyMedium**:
  - 0: kEthernetPhyMediumUnknown
  - 1: kEthernetPhyMediumIEEE_802_3
  - 2: kEthernetPhyMedium100BASE_T1
  - 3: kEthernetPhyMedium1GB_COAX
  - 4: kEthernetPhyMedium1000BASE_T1
  - 5: kEthernetPhyMedium2500BASE_T1
  - 6: kEthernetPhyMedium5000BASE_T1
  - 7: kEthernetPhyMedium10000BASE_T1
  - 8: kEthernetPhyMedium10BASE_T1S

## Return Values

- **0**: Failure
- **1**: Success

## Example

```plaintext
void print()
{
  stack ethernetPort port = ethernetPort::Ethernet1::Port1;
  stack enum EthernetPhyMedium medium;

  if (ethGetPhyMedium(port, medium) != 0)
  {
    printMedium(medium);
  }
}

void printMedium(enum EthernetPhyMedium medium)
{
  char str[64];

  switch (medium)
  {
    case kEthernetPhyMediumUnknown:
      strncpy(str, "kEthernetPhyMediumUnknown", elcount(str));
      break;
    case kEthernetPhyMediumIEEE_802_3:
      strncpy(str, "kEthernetPhyMediumIEEE_802_3", elcount(str));
      break;
    case kEthernetPhyMediumBroadR_Reach:
      strncpy(str, "kEthernetPhyMediumBroadR_Reach", elcount(str));
      break;
    case kEthernetPhyMedium1GB_COAX:
      strncpy(str, "kEthernetPhyMedium1GB_COAX", elcount(str));
      break;
    case kEthernetPhyMedium1000BASE_T1:
      strncpy(str, "kEthernetPhyMedium1000BASE_T1", elcount(str));
      break;
    case kEthernetPhyMedium2500BASE_T1:
      strncpy(str, "kEthernetPhyMedium2500BASE_T1", elcount(str));
      break;
    case kEthernetPhyMedium5000BASE_T1:
      strncpy(str, "kEthernetPhyMedium5000BASE_T1", elcount(str));
      break;
    case kEthernetPhyMedium10000BASE_T1:
      strncpy(str, "kEthernetPhyMedium10000BASE_T1", elcount(str));
      break;
    case kEthernetPhyMedium10BASE_T1S:
      strncpy(str, "kEthernetPhyMedium10BASE_T1S", elcount(str));
      break;
    default:
      write("error");
      return;
  }

  write("medium: %s", str);
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
