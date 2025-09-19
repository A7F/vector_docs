[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpsecPolicyDatabaseAdd.md)

**CAPL Functions** » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » ipsecPolicyDatabaseAdd

# ipsecPolicyDatabaseAdd

Valid for: CANoe DE • CANoe4SW DE

**Note**  
The function is dependent on the selected stack. This functionality cannot be used in connection with the operating system TCP/IP stack.

## Function Syntax

```plaintext
long ipsecPolicyDatabaseAdd(IP_Endpoint source, dword sourcePrefix, IP_Endoint destination, dword destPrefix, char[] nextLayerProtocol, char[] policy);
```

## Description

With this function, it is possible to manually add an IPsec policy to the security policy database of the current network stack. The network stack will check the selectors, and if it finds a match, the traffic will be handled with the given policy.

## Parameters

- **source**: The address and port of the source selector.
- **sourcePrefix**: The prefix of the source selector. This defines which part of the address of the selector is relevant for filtering.
- **destination**: The address and port of the destination selector.
- **destPrefix**: The prefix of the destination sector. This defines which part of the address of the selector is relevant for filtering.
- **nextLayerProtocol**: The upper layer protocol to be used. Can be one of the following protocols:
  - IP_PROTO_ICMP
  - IP_PROTO_TCP
  - IP_PROTO_UDP
  - IP_PROTO_ICMPv6
  - ANY
- **policy**: policy is one of the following formats:
  - `<direction> discard`: This policy will discard all packets which fit the given selectors.
  - `<direction> none`: This policy will do nothing with the packets that fit the given selectors.
  - `<direction> ipsec <protocol>/<mode>/[src-dst]/<level>`: This policy will handle the packet with the given IPsec policy, with:
    - `<direction>`: in|out
      - **in**: policy for incoming data
      - **out**: policy for outgoing data
    - `<protocol>`: ah|esp
      - **ah**: use authentication header
      - **esp**: use encapsulating security payload
    - `<mode>`: tunnel|transport
      - **tunnel**: use tunnel mode. This requires a next parameter of src-dst.
      - **transport**: use transport mode.
    - `[src-dst]`: Is only given if the mode is tunnel
      - **src**: source address of the tunnel
      - **dst**: destination address of the tunnel
    - `<level>`: use|require
      - **use**: use the given policy if a security association is available. Otherwise bypass IPsec.
      - **require**: always use IPsec. Discard the packet if no security association for the current connection is available.

## Return Values

- **0**: Success
- **-1**: Failed

## Example

```plaintext
on start
{
  // bypass IPsec for outgoing packets from any address to the node with address 192.168.1.12 on port 23
  IpSecPolicyDatabaseAdd(ip_Endpoint(0.0.0.0:0), 0, ip_Endpoint(192.168.1.12:23), 32, "any", "out bypass");

  // discard all outgoing packets from any address to the node with address 192.168.1.13 with destination port 23
  IpSecPolicyDatabaseAdd(ip_Endpoint(0.0.0.0:0), 0, ip_Endpoint(192.168.1.13:23), 32, "any", "out discard");

  // Use ah in transport mode on outgoing packets from any address to the node with address 192.168.1.10 to destination port 23. Discard the packet if no security association is available.
  IpSecPolicyDatabaseAdd(ip_Endpoint(0.0.0.0:0), 0, ip_Endpoint(192.168.1.10:23), 32, "any", "out ipsec ah/transport//require");

  // Use esp in transport mode on outgoing packets from any address to the network 192.168.1.0/24 to destination port 21 if a security association is available.
  IpSecPolicyDatabaseAdd(ip_Endpoint(0.0.0.0:0), 0, ip_Endpoint(192.168.1.0:21), 24, "any", "out ipsec esp/transport//use");

  // Use esp in tunnel mode on outgoing packets from any address to the network 192.168.2.0/24 to destination port 22. The tunnel is between 192.168.1.1 and 192.168.2.5. Discard the packet if no security association is available.
  IpSecPolicyDatabaseAdd(ip_Endpoint(0.0.0.0:0), 0, ip_Endpoint(192.168.2.0:22), 24, "any", "out ipsec esp/tunnel/192.168.1.1-192.168.2.5/require");

  // Use ah in tunnel mode on outgoing packets from any address to the network 192.168.2.0/24 to destination port 24. The tunnel is between 192.168.1.1 and 192.168.1.5. Discard the packet if no security association is available.
  IpSecPolicyDatabaseAdd(ip_Endpoint(0.0.0.0:0), 0, ip_Endpoint(192.168.2.0:24), 24, "any", "out ipsec ah/tunnel/192.168.1.1-192.168.1.5/require");
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
