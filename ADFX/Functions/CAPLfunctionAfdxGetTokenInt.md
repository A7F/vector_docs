# AfdxGetTokenInt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxGetTokenInt( long packet, char protocolDesignator[], char tokenDesignator[] ); // form 1
long AfdxGetTokenInt( long packet, char protocolDesignatorl[], char tokenDesignator[], long offset, long length, long networkByteOrder ); // form 2
```

## Description

This function returns the specified token‘s data as an integer value. With additional parameters (form 2) the user may specify the starting byte, length and byte ordering of the extracted integer value.

**Note:** The network byte order interpretation for form 1 is big-endian.

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolsIntro.md), e.g. "afdx".
- **tokenDesignator**: Name of the token, e.g. "lpvSpeed".
- **offset**: This is the offset from the beginning of the token's data area. If this is 0, data is copied starting at byte 0 of the token's data area.
- **length**: This is the length of the integer value to be returned from the token's data area (range 1..4).
- **networkByteOrder**:
  - 0: INTEL (little-endian)
  - 1: MOTOROLA (big-endian)

## Return Values

Integer value gathered from the token's data. With [AfdxGetLastError](CAPLfunctionAfdxGetLastError.md) you have to check if the function has been processed successfully.

## Example

Node **System - preStart** in CAPL Browser

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
  long status;
  char error[100];

  // get status byte 1  of FDS1 (offset=4, length=1byte)
  status = AfdxGetTokenInt( packet, "udp", "data", 4, 1, 1 );
  if (AfdxGetLastError() == 0)
  {
    // do something with status
  }
  else
  {
    AfdxGetLastErrorText( elCount(error), error );
    write("Error: %s", error );
  }
}
```
