[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetInt64.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethernetPacket::GetInt64**

# ethernetPacket::GetInt64

**Valid for**: CANoe DE • CANoe4SW DE

## Method Syntax

```plaintext
int ethernetPacket.GetInt64(char protocol[], char field[]);
```

## Description

Returns the value of the specified field as **int64**.

If **protocol** or **field** is not contained in the packet, the measurement is stopped with a runtime error. [ethernetPacket::IsAvailable](CAPLfunctionIsAvailable.md) can be used to find out if the field is available.

## Parameters

- **protocol**: Name of the [protocol](../../../CANoeCANalyzer/Ethernet/Protocols/Protocol.md).
- **field**: Name of the field.

## Return Values

Value of the field.

## Example

```plaintext
on ethernetPacket *
{
  if(this.IsAvailable("ipv4", "source"))
  {
    Write("ipv4.source has value 0x%lX", this.GetInt64("ipv4", "source"));
  }
}
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
