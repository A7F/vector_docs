[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/EventProcedures/CAPLfunctionTCPIPOnIpAddressRemoved.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » OnIpAddressRemoved

# OnIpAddressRemoved

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnIpAddressRemoved(dword ifIndex, ip_address address, dword prefix, dword origin);
```

## Description

If the CAPL program implements this callback it is called when an address gets removed from a network interface.

**Note**: The callback is only available for simulation nodes using the individual TCP/IP stack instance. Check this setting in the CANoe DE product [TCP/IP Stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md) configuration dialog.

## Parameters

- **ifIndex**: The 1-based network interface index.
- **address**: The removed IP address.
- **prefix**: The prefix of the removed address. It defines the number of bits belonging to the network part of the address.
- **origin**: Defines the initiator for removing this address. Possible values are:
  - ORIGIN_UNKNOWN = 0,
  - ORIGIN_USER = 1,
  - ORIGIN_SYSTEM = 2,
  - ORIGIN_DHCPv4CLIENT = 3,
  - ORIGIN_DHCPv6CLIENT = 4,
  - ORIGIN_RFC3927CLIENT = 5

## Return Values

—

## Example

```plaintext
void OnIpAddressRemoved(dword ifIndex, ip_Address address, dword prefix, dword origin)
{
  char addrString[50];
  char originNames[6][25] = {"ORIGIN_UNKNOWN", "ORIGIN_USER", "ORIGIN_SYSTEM", "ORIGIN_DHCPv4CLIENT", "ORIGIN_DHCPv6CLIENT", "ORIGIN_RFC3927CLIENT"};
  address.PrintAddressToString(addrString);
  snprintf(addrString, elcount(addrString), "%s/%d", addrString, prefix);
  write("removed ip address: %s from adapter nr: %d. Origin: %s", addrString, ifIndex, originNames[origin]);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
