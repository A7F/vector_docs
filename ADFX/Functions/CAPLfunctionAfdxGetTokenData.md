[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxGetTokenData.md)

**CAPL Functions** » **AFDX** » **AfdxGetTokenData**

# AfdxGetTokenData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxGetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long offset, long length, byte buffer[] ); // form 1
long AfdxGetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long offset, long length, char buffer[] ); // form 2
long AfdxGetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long offset, long length, struct * buffer ); // form 3
```

## Description

This function copies a number of bytes from a token's data area to a destination buffer.

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolsIntro.md), e.g. "afdx".
- **tokenDesignator**: Name of the token, e.g. "data".
- **offset**: This is the offset from the beginning of the token's data area. If this is 0, data is copied starting at byte 0 of the token's data area.
- **length**: This is the number of bytes to be copied from the token's data area to the specified buffer.
- **buffer**: This is the destination buffer for the copied data. Make sure that the size of the buffer is at least **length** bytes.

## Return Values

- Number of copied bytes or 0
- With [AfdxGetLastError](CAPLfunctionAfdxGetLastError.md) you can check if the function has been processed successfully.

## Example

```plaintext
Node System - preStart in CAPL Browser

on preStart
{
  AfdxRegisterReceiveCallback ( "OnAfdxPacket");
}

Node Callback Function in CAPL Browser

void OnAfdxPacket( long dir, long line, int64 timestamp, long bag, long afdxFlags, long packet )
{
  byte data[8];
  char error[100];

  // get first 8 byte (FS) of payload of the receive packet
  AfdxGetTokenData( packet, "afdx", "data", 0, 8, data );
  if (AfdxGetLastError() == 0)
  {
    // do something with data
  }
  else
  {
    AfdxGetLastErrorText( elCount(error), error );
    write("Error: %s", error );
  }
}
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)