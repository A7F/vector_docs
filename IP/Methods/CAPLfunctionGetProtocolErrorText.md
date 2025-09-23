[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionGetProtocolErrorText.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::GetProtocolErrorText

# ethernetPacket::GetProtocolErrorText

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

- `word ethernetPacket.GetProtocolErrorText( char buffer[] ); // form 1`
- `word ethernetPacket.GetProtocolErrorText( dword format, char buffer[] ); // form 2`

## Description

Copies an error text to the buffer for invalid Ethernet packets. For valid Ethernet packets, an empty string is returned. If format is specified, you can obtain corresponding information, e.g. `Error [IPv4-005]: Checksum is not correct`.

## Parameters

- **buffer**  
  Char buffer where the error string is copied to.

- **format**  
  - 0: only error text (same as form 1)
  - 1: error text, severity and error number
  - 2: error number only

## Return Values

Number of characters copied to buffer.

## Example

```plaintext
on ethernetPacket *
{
  if (this.HasProtocolError())
  {
    char text[100];
    this.GetProtocolErrorText( text );
    // this.GetProtocolErrorText(1, text); // more information
    write( "Protocol error on Eth %d: %s", this.msgChannel, text );
  }
}
```
