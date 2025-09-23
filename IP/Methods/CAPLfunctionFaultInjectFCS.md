[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionFaultInjectFCS.md)

**CAPL Functions » Ethernet » Function Overview » ethernetPacket::FaultInjectFCS**

# ethernetPacket::FaultInjectFCS

[Valid for: CANoe DE • CANoe4SW DE](../../../Shared/FeatureAvailability.md)

## Method Syntax

dword [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md).FaultInjectFCS ( word fcs );

## Description

Set the frame checksum of the packet to an invalid value, which is not recalculated on sending.

**Note**

- Only supported with Vector Ethernet network interfaces.
- Same behavior as [output( ethernetpacket, word fcs )](../Functions/CAPLfunctionOutputEthernet.md).

## Parameters

- **fcs**: Ethernet packet check sequence.

## Return Values

- **0**: success

## Example

—

[See Also](javascript:void(0);)
