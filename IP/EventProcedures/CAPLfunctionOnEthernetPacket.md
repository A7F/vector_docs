# on ethernetPacket

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/EventProcedures/CAPLfunctionOnEthernetPacket.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » on ethernetPacket

## Function Syntax

- `on ethernetPacket *; // form 1`
- `on ethernetPacket msgChannel<X>.*; // form 2`
- `on ethernetPacket ethernetPort::<Network>::<PortName>.*; // form 3`

## Description

The event procedure is called on the receipt of a valid Ethernet packet. To access the control information you would use **selectors**. The keyword [this](../../Other/EventProcedures/CAPLfunctionKeywordThis.md) is available within an **on ethernetPacket** procedure, to access the data of the packet that has just been received.

CAPL programs are by default not transparent to bus events. This means that a CAPL node in the evaluation branch of the measurement configuration will block the data flow to its right side. You must explicitly program the passing of messages in CAPL nodes in the evaluation branch.

To make the CAPL node transparent to messages you would write:

```plaintext
on ethernetPacket *
{
    output(this);
};
```

## Parameters

- **msgChannel`<X>`**: Ethernet channel number, range 1..32.
- **ethernetPort::`<NetworkName>`::`<PortName>`**: Ethernet port qualification.

## Selectors

See [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md)

## Example

**Example 1**

```plaintext
on ethernetPacket *
{
    write("Received Ethernet packet on Eth%d", this.msgChannel );
    output( this ); // only required in CAPL node in measurement setup!
}
```

**Example 2**

```plaintext
on ethernetPacket msgChannel1.*
{
    write("Received Ethernet packet with length %d", this.Length );
    output( this ); // only required in CAPL node in measurement setup!
}
```

**Example 3**

```plaintext
on ethernetPacket ethernetPort::Ethernet1::HU.*
{
    write("Received Ethernet packet with length %d", this.Length );
    output( this ); // only required in CAPL node in measurement setup!
}
```

[See Also](javascript:void(0);)
