[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionFDXClientHandleUdp.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » FDXClientHandleUdp

# FDXClientHandleUdp

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long FDXClientHandleUdp(dword ipv4Address, dword port); // form 1`
- `long FDXClientHandleUdp(byte ipv6Address[], dword port); // form 2`

## Description

This function creates an FDX client handle for the FDX client with the specified address.

Prerequisite for the function is to configure **UPD/IPv4** or **UDP/IPv6** as transport layer for the FDX feature.

## Parameters

- **ipv4Address**: IPv4 address of the FDX clients
- **ipv6Address**: IPv6 address of the FDX clients
- **port**: UPD port number of the FDX clients.

## Return Values

If successful, the function returns a value greater than 0, which means the FDX client handle. Values smaller than or equal to zero indicate an error.

- **-1**: The FDX feature is disabled in the CANoe DE product configuration or configured for another transport layer.

## Example

**Example for UDP/IPv4**

```plaintext
long fdxClientHandle = 0;
dword fdxClientPort = 0;
dword fdxClientAddr = 0;

fdxClientAddr = IpGetAddressAsNumber("127.0.0.1");
fdxClientPort = 2810;
fdxClientHandle = FDXClientHandleUdp(fdxClientAddr, fdxClientPort);
```

**Example for UDP/IPv6**

```plaintext
long  fdxClientHandle = 0;
dword fdxClientPort = 0;
byte  fdxClientAddr[16];

IpGetAddressAsArray("::1", fdxClientAddr);
fdxClientPort = 2820;
fdxClientHandle = FDXClientHandleUdp(fdxClientAddr, fdxClientPort);
```

[Coupling of two CANoe Instances using the FDX Protocol](../../../CANoeCANalyzer/Interfaces/FDXProtocolCouplingCANoeInstances.md) • [FDXClientHandleTcp](CAPLfunctionFDXClientHandleTcp.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
