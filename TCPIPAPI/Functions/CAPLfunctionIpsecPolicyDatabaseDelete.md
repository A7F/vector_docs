[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpsecPolicyDatabaseDelete.md)

**CAPL Functions** » **TCP/IP API** » **ipsecPolicyDatabaseDelete**

# ipsecPolicyDatabaseDelete

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
The function is dependent on the selected stack. This functionality cannot be used in connection with the operating system TCP/IP stack.

## Function Syntax

```plaintext
long ipsecPolicyDatabaseDelete(IP_Endpoint source, dword srcPrefix, IP_Endoint destination, dword destPrefix, char[] nextLayerProtocol, char[] policy);
```

## Description

With this function it is possible to manually delete a single ipsec policy from the security policy database of the current network stack. The policy to delete is defined by its selectors and the direction (incoming or outgoing).

## Parameters

- **source**: The address and port of the source selector.
- **sourceFix**: The prefix of the source selector.
- **destination**: The address and port of the destination selector.
- **destPrefix**: The prefix of the destination sector.
- **nextLayerProtocol**: The upper layer protocol to be used. Can be one of the following protocols:
  - IP_PROTO_ICMP
  - IP_PROTO_TCP
  - IP_PROTO_UDP
  - IP_PROTO_ICMPv6
  - ANY
- **policy**:
  - **in**: delete an incoming policy
  - **out**: delete an outgoing policy

## Return Values

- **0**: Success
- **-1**: Failed

## Example

```plaintext
on start
{
  // delete the outgoing policy from any address to port 21 on the network 192.168.1.0/24
  IPsecPolicyDatabaseDelete(ip_Endpoint(0.0.0.0:0), 0, ip_Endpoint(192.168.1.0:21), 24, "any", "out");
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
