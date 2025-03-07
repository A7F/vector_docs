[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionA664isICMP.md)

CAPL Function Overview » [AFDX »](../CAPLfunctionsAFDXOverview.md) A664isICMP

# A664isICMP

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

1. `long A664isICMP (a664Frame aFrame, dbNode NodeName)`
2. `long A664isICMP (a664Frame aFrame, dword dstIP, word VLid)`

## Description

This function returns the ICMP type and code for a packet. The intended use case is a check for an expected ICMP packet in an on-handler. The packet is checked according to the following rules:

- IP protocol number is set to 1
- VL of parameter `aFrame` ([selector EthVlId](../CAPLfunctionsAFDXSelectors.md#EthVlId)) corresponds to
  - calling convention (1): DBC attribute [ICMP_inVLid](../../../CANoeCANalyzer/AFDX/afdxDBsupport/afdxDBsupportNodeAttributes.md#ICMP_inVLid)
  - calling convention (2): parameter `VLid`
- destination IP address of parameter `aFrame` ([selector IpAdrDst](../CAPLfunctionsAFDXSelectors.md#IpAdrDst)) corresponds to
  - calling convention (1): DBC attribute [ICMP_destIP](../../../CANoeCANalyzer/AFDX/afdxDBsupport/afdxDBsupportNodeAttributes.md#ICMP_destIP)
  - calling convention (2): parameter `dstIp`

## Parameters

- **aFrame**: The frame object of type [a664Frame](../../../CANoeCANalyzer/AFDX/capl/afdxDefineAFDXframe.md) to be checked.
- **NodeName**: (1) This is the name of a node from the assigned DBC. The DBC must be an AFDX DBC file and the necessary [attributes](../../../CANoeCANalyzer/AFDX/afdxDBsupport/afdxDBsupportNodeAttributes.md) must exist.
- **dstIP**: (2) destination IP address to be used for check.
- **VLid**: (2) VLId to be used for check.

## Return Values

- **<success>**: `0x0000<ICMP type><ICMP code>`
  - `0x00000000`: Ping Request received (type = 0; code = 0);
  - `0x00000800`: Echo Reply received (type = 8; code = 0);
- **<error> -1**: IP protocol is not ICMP
- **<error> -2**: no ICMP attributes found for `NodeName`
- **<error> -3**: invalid IP address value
- **<error> -4**: unsupported ICMP type
- **<error> -6**: invalid VL value

## Example

—

[See Also](javascript:void(0);)