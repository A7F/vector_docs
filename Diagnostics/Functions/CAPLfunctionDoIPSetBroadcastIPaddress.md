# DoIP_SetBroadcastIPaddress

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetBroadcastIPaddress(char broadcastAddress[]);
```

## Description

Sets target IP address for broadcast messages sent from this node.

## Parameters

- **broadcastAddress**

  - `255.255.255.255`: send a limited broadcast (default if IPv4 is active)
  - `""` (empty string): send a directed broadcast, deriving address from local IPv4 address
  - other: if this is a valid string representation of an IP address, send to this address, e.g. a broadcast directed to a different network, or an IPv6 multicast address

## Return Values

—

## Example

```plaintext
DoIP_SetLocalIPaddress("192.168.1.123");
if (sendDirectedBroadcast)
  DoIP_SetBroadcastIPaddress(""); // send to 192.168.1.255
else if (sendToOtherNetwork)
  DoIP_SetBroadcastIPaddress("192.168.5.255"); // send to 192.168.5.255
else // restore default
  DoIP_SetBroadcastIPaddress("255.255.255.255"); // limited broadcast
```

[DoIP_SetLocalIPaddress](CAPLfunctionDoIPSetLocalIPaddress.md)
