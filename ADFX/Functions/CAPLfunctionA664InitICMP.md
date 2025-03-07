[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionA664InitICMP.md)

# A664InitICMP

**CAPL Functions** » **AFDX »** A664InitICMP

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

1. `long A664InitICMP (a664Frame aFrame, dword InitType, word payloadSize, dbNode NodeName)`
2. `long A664InitICMP (a664Frame aFrame, dword InitType, word payloadSize, dword srcIP, dword dstIP, word VLid)`

## Description

The complete Ethernet and IP headers of an AFDX packet are consistently set based on the given parameters. With calling convention (1), the initialization values are given in the attributes of a DBC object. Calling convention (2) is intended for full user-control of all the parameters. In this case, it is necessary to configure the corresponding VL, too. Otherwise, the VL definition is not complete and it is not possible to schedule the ICMP frame. Use the function [A664VLConfig](CAPLfunctionA664VLConfig.md) for setting detailed VL parameters.

The IP payload area is initialized according to the parameter `InitType`. There are three different values possible for this parameter.

- **The `InitType` = `SWAP_ADR`** is intended for creating the ECHO REPLY out of a received packet. In this case, the parameter `payloadSize` is ignored. The IP addresses (contents of the selectors [IpAdrDst](../CAPLfunctionsAFDXSelectors.md#IpAdrDst) and [IpAdrSrc](../CAPLfunctionsAFDXSelectors.md#IpAdrSrc)) are swapped. ICMP type and code are set to ECHO REPLY.
  - (1) The VL for the packet is taken from the DBC attribute [ICMP_outVLid](../../../CANoeCANalyzer/AFDX/afdxDBsupport/afdxDBsupportNodeAttributes.md#ICMP_outVLid) and the MAC addresses are adapted accordingly. Note that the ICMP payload is not modified.
  - (2) The parameters `srcIP` and `dstIP` are ignored. The VL for the packet is taken from parameter `VLid` and the MAC addresses are adapted accordingly. Note that the ICMP payload is not modified.

- **The values `InitType` = `ECHO_REPLY` or `PING_REQ`** are used to initialize a newly created packet. The ICMP payload area is created according to `payloadSize` and set to 0. Furthermore, ICMP type and code are set.
  - (1) The source IP address (selector [IpAdrSrc](../CAPLfunctionsAFDXSelectors.md#IpAdrSrc)) is taken from the initialization file `CAN.INI` (section = `AFDX`; value = `DefaultSrcIP`). The VL-related configuration is given from the DBC object.
  - (2) The function provides the complete addressing information. Note that the function [A664VLConfig()](CAPLfunctionA664VLConfig.md) has to be called for setting detailed VL parameters.

**Note**: A multicast IP address value is not allowed for ICMP.

## Parameters

- **aFrame**: The frame object to be initialized
- **InitType**:
  - 1: ECHO_REPLY: initializes the type/code to ECHO REPLY
  - 8: PING_REQ: initializes the type/code to PING REQUEST
  - 256: SWAP_ADR: swaps addressing information (source/destination MAC and IP addresses), initializes the type/code to ECHO REPLY, the parameter payloadSize is ignored
- **payloadSize**: size of the optional ICMP payload places after the ICMP header (corresponds to the bytes in IpPayload following the ICMP header). The valid range is [0 .. [ICMP_outVLbufSize](../../../CANoeCANalyzer/AFDX/afdxDBsupport/afdxDBsupportNodeAttributes.md#ICMP_outVLbufSize) / [ICMP_inVLbufSize](../../../CANoeCANalyzer/AFDX/afdxDBsupport/afdxDBsupportNodeAttributes.md#ICMP_inVLbufSize)]
  - This parameter is ignored if `InitType` is set to `SWAP_ADR`.
- **NodeName**: (1) This is the name of a node from the assigned DBC. The DBC must be an AFDX DBC file and the necessary [attributes](../../../CANoeCANalyzer/AFDX/afdxDBsupport/afdxDBsupportNodeAttributes.md) must exist.
- **srcIP**: (2) source IP address to be used for the Eth- and IP-headers. This parameter is ignored if `InitType` is set to `SWAP_ADR`.
- **dstIP**: (2) destination IP address to be used for the IP-headers. This parameter is ignored if `InitType` is set to `SWAP_ADR`.
- **VLid**: (2) VLId to be used for the destination Eth-header (see selector [EthVlId](../CAPLfunctionsAFDXSelectors.md#EthVlId))

## Return Values

- `<success> 0`: No error.
- `<error> -1`: Invalid `InitType`.
- `<error> -2`: No ICMP attributes found for `NodeName`.
- `<error> -3`: Invalid IP address value.
- `<error> -4`: Payload size exceeds [MaxFrameSize](../../../CANoeCANalyzer/AFDX/afdxDBsupport/afdxDBsupportMessageAttributes.md#AfdxVLmaxFrame).
- `<error> -5`: Protocol, IP-addr or VLid of incoming frame are invalid in case of SWAP_ADR.
- `<error> -6`: Setting the checksum failed.

## Example

**Create ICMP frames from DBC attributes**

```c
includes
{
  #include "AFDX/utils.cin"
}
…
on key 'p'  // generate ping-request using DBC info
{
  a664Frame *fr = { msgChannel = 1 };
  // use equipment info of LI_SDF_3 from DBC to specify icmp-configuration
  a664InitICMP(fr, PING_REQ, LI_SDF_3.ICMP_outVLbufSize, LI_SDF_3);
  a664TriggerFrame(fr, 1); // single shot, but respect BAG
}
```

**Create ICMP frames manually**

```c
includes
{
  #include "AFDX/utils.cin"
}
….
on key 'P'  // generate ping-request manually
{
  a664Frame *fr = { msgChannel = 1 };
  DWORD srcIP, dstIP;
  srcIP = IpGetAddressAsNumber("10.1.38.1");
  dstIP = IpGetAddressAsNumber("10.2.38.2");
  a664InitICMP(fr, PING_REQ, 16, srcIP, dstIP, 6673);
  a664TriggerFrame(fr, 1);  // single shot, but respect BAG
}
```