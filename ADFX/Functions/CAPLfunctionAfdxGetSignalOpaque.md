# AfdxGetSignalOpaque

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long AfdxGetSignalOpaque( long packet, char signalName[], long bufSize, byte buffer[] ); // form 1`
- `long AfdxGetSignalOpaque( long packet, long offset, long bufSize, byte buffer[] ); // form 2`
- `long AfdxGetSignalOpaque( long packet, long offset, long length, long bufSize, byte buffer[] ); // form 3`

## Description

This function copies the content of an opaque data to the specified buffer. There are two different opaque data types available in AFDX:

- Fixed length opaque data: n bytes (form 3 only)
- Variable length opaque type: 16-bit length value n, data field filled up with n bytes, padding area filled with 0 (form 2 only)

Since the opaque type is not detectable from the payload stream it must be described explicitly by the network designer.

## Parameters

- **packet**: Handle of the message.
- **signalName**: Name of the signal.  
  **Note:** The signal, the signal’s data type and the message need to be defined in the assigned DBC file.
- **offset**: The offset value points to the starting byte of the opaque signal in the AFDX payload area.
- **bufSize**: Size of available buffer area.
- **length**: This is the number of bytes to be copied from the fixed size opaque signal to the specified buffer.
- **buffer**: Buffer containing the read data.  
  Make sure that the size of the buffer is at least **length** bytes.

## Return Values

- Number of copied data bytes.
- If this value is > **bufSize** an error occurred.

## Example

**Analyze signals from an incoming AFDX packet using DBC information**

```plaintext
on preStart
{
  AfdxRegisterReceiveCallback("OnPacket");
}

void OnPacket( long dir, long line, int64 timestamp, long bag, long afdxFlags, long packet )
{
  long lVal=0; // integer signal
  long eVal=0; // enumeration signal
  long bVal=0; // boolean signal
  double rVal = 0.0; // float signal
  char sVal[16]; // string signal
  byte oVal[16]; // opaque signal
  long len, status, err;
  long msgID;
  char msgName[256];

  // get message ID of this message
  msgID = AfdxGetMessageId( packet );

  // get message name of this message
  err = AfdxGetMessageName( packet, 256, msgName );

  // get signal status
  status = AfdxGetSignalStatus( packet, "VFG_OIL_TEMP_A_34" );

  // get integer signal
  lVal = AfdxGetSignalInt( packet, "VFG_OIL_TEMP_A_34" );

  // get float-signal 2
  rVal = AfdxGetSignalReal( packet, "VFG_OIL_TEMP_AB_32" );

  // get boolean signal 3
  bVal = AfdxGetSignalBool( packet, "VFG_OIL_TEMP_A_ON" );

  // get enumeration signal 4
  eVal = AfdxGetSignalInt( packet, "FLIGHT_GROUND_COND_3" );

  // get string signal 6
  len = AfdxGetSignalString( packet, "TEST_STRING14_CITY", 16, sVal );

  // get opaque signal 7
  len = AfdxGetSignalOpaque( packet, "TEST_OPAQUE14_IDENT", 16, oVal );
}
```
