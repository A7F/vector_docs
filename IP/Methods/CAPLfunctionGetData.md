[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetData.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethernetPacket::GetData**

# ethernetPacket::GetData

**Valid for**: CANoe DE • CANoe4SW DE

## Method Syntax

- `word ethernetPacket.GetData(word offset, char dest[], word length); // form 1`
- `word ethernetPacket.GetData(word offset, byte dest[], word length); // form 2`
- `word ethernetPacket.GetData(word offset, struct * dest); // form 3`
- `word ethernetPacket.GetData(word offset, sysvarStruct dest); // form 4`
- `word ethernetPacket.GetData(char protocol[], char field[], byte dest[]); // form 5`

## Description

Copies the data of an Ethernet packet to a byte array, char array, CAPL struct or system variable struct.

## Parameters

- **offset**: Byte offset of the data in the Ethernet packet. Offset 0 is the byte directly after the Ethertype.
- **dest**: Destination where the data is copied to.
- **length**: Number of bytes to copy.

## Return Values

Number of bytes copied to the destination buffer.

## Example

```plaintext
on ethernetPacket *
{
  dword ipHeaderLength;
  byte  ipProtocol;

  switch(this.type)
  {
    case 0x0800: // IPv4
      ipHeaderLength = (this.Byte(0) & 0x0F) * 4;
      ipProtocol     = this.Byte(9);

      switch(ipProtocol)
      {
        case 17:
          HandleUDP( this, ipHeaderLength+8, swapWord(this.Word(ipHeaderLength)), swapWord(this.Word(ipHeaderLength+2)) );
          break;
      }

      break;
  }

  if(this.IsAvailable("tcp", "data"))
  {
    byte buffer[1500];
    word payloadLength;
    payloadLength = this.GetData("tcp", "data", buffer);
    write("tcp payload length: %d", payloadLength);
  }
}

void HandleUDP( ethernetPacket * pkt, word udpDataOffset, word srcPort, word dstPort )
{
  char buffer[100];
  word length;

  length = pkt.GetData( udpDataOffset, buffer, elcount(buffer)-1 );
  buffer[length] = 0; // terminating zero for strings

  write( "UDP (port 0x%X to 0x%X): %s", srcPort, dstPort, buffer );
}
```
