[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/EventProcedures/CAPLfunctionOnEthernetErrorPacket.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **on ethernetErrorPacket**

# on ethernetErrorPacket

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `on ethernetErrorPacket *;` // form 1
- `on ethernetErrorPacket msgChannel<X>.*;` // form 2
- `on ethernetErrorPacket ethernetPort::<Network>::<PortName>.*;` // form 3

## Description

The event procedure is called on the receipt of an invalid Ethernet packet with checksum or length error.

To access the control information you would use **selectors**.

The keyword [this](../../Other/EventProcedures/CAPLfunctionKeywordThis.md) is available within an **on ethernetErrorPacket** procedure, to access the data of the packet that has just been received.

CAPL programs are by default not transparent to bus events. This means that a CAPL node in the evaluation branch of the measurement configuration will block the data flow to its right side. You must explicitly program the passing of messages in CAPL nodes in the evaluation branch.

To make the CAPL node transparent to messages you would write:

```plaintext
on ethernetErrorPacket *
{
  output(this);
};
```

## Parameters

- **msgChannel`<X>`**: Ethernet channel number, range 1..32.
- **ethernetPort::`<NetworkName>`::`<PortName>`**: Ethernet port qualification.

## Selectors

See [ethernetErrorPacket](../Objects/CAPLfunctionEthernetErrorPacket.md)

## Example

```c
on ethernetErrorPacket *
{
  write("Received Ethernet error packet on Eth%d", this.msgChannel );
  output( this ); // only required in CAPL node in measurement setup!
}

on ethernetErrorPacket ethernetport::SpecialV30::ECU_1.*
{
  write ("ON ethernetErrorPacket ethernetport::SpecialV30::ECU_1.*: Ch:%d, PortId:%d", this.msgChannel, this.hwPort.portId);
}
```

[See Also](javascript:void(0);)

**CANoe (Desktop Editions & Test Bench Editions)** Version **18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
