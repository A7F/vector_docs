[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionOnAvbSendPrepare.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **OnAvbSendPrepare**

# OnAvbSendPrepare

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long OnAvbSendPrepare( dword talkerHandle, ethernetPacket * packet);
```

## Description

If the CAPL program implements this callback it is called right before a packet will be sent by the AVB stack. Currently only packets of an AVTP stream are supported.

It is possible to manipulate the content of the packet or to block the sending of the packet on the network.

## Parameters

- **talkerHandle**: The Talker handle.
- **packet**: The Ethernet packet which will be send.

## Return Values

- **0**: Block the Ethernet packet.
- **1**: Send the Ethernet packet.

## Example

—

[See Also](javascript:void(0);)
