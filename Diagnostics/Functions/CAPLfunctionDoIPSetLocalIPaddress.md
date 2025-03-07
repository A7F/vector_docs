[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPSetLocalIPaddress.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_SetLocalIPaddress

# DoIP_SetLocalIPaddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The local IP address can be set to restrict sending and receiving to a specific adapter, i.e. broadcasts will not be sent on all available adapters. If a tester shall communicate with a vehicle located at a known IP address, it suffices to use [DoIP_SetVehicleAddress](CAPLfunctionDoIPSetVehicleAddress.md) and let the IP stack find a suitable adapter.

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
long DoIP_SetLocalIPaddress(char ipAddress[]);
```

## Description

Set local IP address to bind to.  
In an ECU simulation, Vehicle Announcement Messages (VAM) will be sent from this IP address, in a tester node the Vehicle Identification Request (VIR) messages. If the tester node sets IP address in on prestart, it can receive VAMs even before it sends VIR messages itself. The target IP address is derived from this IP address: for an IPv4 address the broadcast address is determined using the network mask, for an IPv6 address the multicast address is used.

**Note**  
If diagnostics communication is performed on a built-in channel (i.e. the tester node does not configure DoIP.DLL as a node-layer module), this function cannot be used. The address configured in the [Vehicle Simulation Parameter](../../../CANoeCANalyzer/Diagnostics/DoIP/DiagnosticsDoIPNetworkSettings.md) area is used instead.

## Parameters

- **ipAddress**  
  Textual representation of the IP address to bind to, e.g. **192.169.2.22** for an IPv4 address, or **2001::1234** for an IPv6 address. An empty string may be given to reset the stored address, e.g. if the address of an adapter shall be retrieved in a later step.

## Return Values

- **0**  
  Success

- **-10**  
  Invalid address string given

## Example

```plaintext
DoIP_SetLocalIPaddress("10.10.10.222"); // Set an IPv4 address
...
DoIP_SetLocalIPaddress("2001::2222");   // Set an IPv6 address
...
// retrieve the IP address configured for this simulation node's TCP/IP stack
ipGetAdapterAddressAsString(1, localAddr, elcount(localAddr));
// and use it as local address
DoIP_SetLocalIPaddress(localAddr);
```

[DoIP_SetVehicleAdapter](CAPLfunctionDoIPSetVehicleAdapter.md) • [DoIP_SetTesterAdapter](CAPLfunctionDoIPSetTesterAdapter.md) • [DoIP_SetVehicleAddress](CAPLfunctionDoIPSetVehicleAddress.md) • [IpGetAdapterAddressAsString](../../TCPIPAPI/Functions/CAPLfunctionIPGetAdapterAddressAsString.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)