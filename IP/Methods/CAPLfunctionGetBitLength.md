[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetBitLength.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethernetPacket::GetBitLength**

# ethernetPacket::GetBitLength

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Method Syntax

`dword ethernetPacket.GetBitLength(char protocol[], char field[]);`

## Description

Returns the number of bits of the specified field as **dword**.

If **protocol** or **field** is not contained in the packet, the measurement is stopped with a runtime error. [ethernetPacket::IsAvailable](CAPLfunctionIsAvailable.md) can be used to find out if the field is available.

## Parameters

- **protocol**: Name of the [protocol](../../../CANoeCANalyzer/Ethernet/Protocols/Protocol.md).
- **field**: Name of the field.

## Return Values

Number of bits.

## Example

```plaintext
on ethernetPacket *
{
  if(this.IsAvailable("icmpv4", "echo.identifier"))
  {
    Write("icmpv4.echo.identifier bit length: %ld", this.GetBitLength("icmpv4", "echo.identifier"));
  }
}
```

[See Also](javascript:void(0);)