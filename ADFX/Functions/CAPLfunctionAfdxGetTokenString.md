# AfdxGetTokenString

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxGetTokenString.md)

**CAPL Functions** » **AFDX** » AfdxGetTokenString

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxGetTokenString( long packet, char protocolDesignator[], char tokenDesignator[], long offset, long bufSize, char buffer[] );
```

## Description

This function copies characters from the token and adds a terminating "\0".

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolsIntro.md), e.g. "afdx".
- **tokenDesignator**: Name of the token, e.g. "data".
- **offset**: This is the offset from the beginning of the token's data area. If this is 0, data is copied starting at byte 0 of the token's data area.
- **bufSize**: Size of buffer in bytes. This function adds a terminating "\0". Thus the maximum number of copied characters is length-1.
- **buffer**: The characters are copied to this buffer area.

## Return Values

Number of copied characters or 0. With [AfdxGetLastError](CAPLfunctionAfdxGetLastError.md) you have to check if the function has been processed successfully.

## Example

Node **System - PreStart** in CAPL Browser

```plaintext
on preStart
{
  AfdxRegisterReceiveCallback ( "OnAfdxPacket");
}
```

Node **Callback Function** in CAPL Browser

```plaintext
void OnAfdxPacket( long dir, long line, int64 timestamp, long bag, long afdxFlags, long packet )
{
  char rx_str[100];
  char error[100];

  // get a string value located in FDS1
  long offset = 8; // FDS1 + 2 byte length info
  long status  = 0;
  long len = 0;

  len = AfdxGetTokenInt( packet, "udp", "data", offset, 2, 1 );

  if (AfdxGetLastError() == 0)
  {
    AfdxGetTokenString( packet, "udp", "data", offset+2,  len, rx_str );
    if (AfdxGetLastError() == 0)
    {
      write(rx_str);
    }
  }
  else
  {
    AfdxGetLastErrorText( elCount(error), error );
    write("Error: %s", error );
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)