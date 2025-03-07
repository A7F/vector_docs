# AfdxRegisterReceiveCallback

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxRegisterReceiveCallback.md)

**CAPL Functions** » **AFDX** » **AfdxRegisterReceiveCallback**

## Function Syntax

```plaintext
long AfdxRegisterReceiveCallback( char callback[] ); // form 1
long AfdxRegisterReceiveCallback( char callback[], long direction, long dropped, long type ); // form 2
```

## Description

Use this function to register a CAPL [callback](../EventProcedures/CAPLfunctionOnAfdxPacket.md) to handle AFDX related events.

Calling the function with form 1 is equivalent to calling it with form 2 with the additional parameters set to these values:

- direction: BothDirections
- dropped: DroppedAndNotDropped
- type: ValidPackets

## Parameters

- **callback**: Name of CAPL callback.

- **direction**: Specifies the direction for the packet or fragment, the callback will be called.
  - 0: RxDirection
  - 1: TxDirection
  - 2: BothDirections

- **dropped**: Specifies if the callback shall be called for dropped packets or fragments.
  - 0: Dropped
  - 1: NotDropped
  - 2: DroppedAndNotDropped

- **type**: Specifies if the callback shall be called for every kind of frame or just for complete and error free IP fragments or packets.
  - 0: ValidPackets
  - 1: ValidFragments
  - 2: EveryFrameAndPacket

## Return Values

- **0**: 
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

Node **System - PreStart** in CAPL Browser

```plaintext
on preStart
{
  AfdxRegisterReceiveCallback( "OnAfdxPacket");
}
```

Node **Callback Function** in CAPL Browser

```plaintext
void OnAfdxPacket( long dir, long line, int64 time, long bag, long afdxFlags, long packet )
{
  byte rawdata[2330];
  long value;
  long rxLength;
  long packetHandle;
  long err;
  char msgName[256];
  dword gContextAfdx1 = 0;
  dword gContextAfdx2 = 0;

  if (!((long)AFDXFlagFrameIsFragment & afdxFlags ))
  {
    // gets the message name of this message
    err = AfdxGetMessageName( packet, 256, msgName );
    if (err > 0) {
      write("AfdxGetMessageName: Message name could not be read");
    }
    if (strncmp ( msgName , "DEMOMSG_INT3" , strlen ("DEMOMSG_INT3") ) == 0)
    {
      // copies the packet content to a local buffer.
      rxLength = AfdxGetPacketData( packet, 0 , elCount(rawdata), rawdata );
      // Returns the context of the specified bus.
      gContextAfdx1 = GetBusNameContext( "AFDX1" );
      gContextAfdx2 = GetBusNameContext( "AFDX2" );
      if ( 0 == gContextAfdx1) {
        writeex( 0, 3, "Error: Cannot determine context for bus: AFDX1");
      }
      if ( 0 == gContextAfdx2) {
        writeex( 0, 3, "Error: Cannot determine context for bus: AFDX2");
      }

      // Check the current bus context of the CAPL block.
      if (GetBusContext() == gContextAfdx1)
      {
        // Sets the bus context of the CAPL block.
        SetBusContext( gContextAfdx2 );
        // Check the bus context of the CAPL block.
        if (GetBusContext() != gContextAfdx2) {
          return;
        }
        // creates a new AFDX packet. Other functions can access to the newly
        // created packet with the returned handle.
        packetHandle = AfdxInitPacket( rxLength, rawdata );
        // check returned handle.
        if ( packetHandle == 0) {
          return;
        }

        // sets the length of a token.
        AfdxResizeToken(packetHandle, "eth", "data", (rxLength-14)*8);
        // gets the content of an AFDX integer signal (32 bit) within a packet,
        // with or without DBC information.
        value = AfdxGetSignalInt( packetHandle, "IOM_DEMO_VFG_OIL_TEMP_A_33" );
        // sets the content of an AFDX integer signal (32 bit) within a packet,
        // with or without DBC information.
        AfdxSetSignalInt( packetHandle, "IOM_DEMO_VFG_OIL_TEMP_A_33", value *2);
        AfdxOutputPacketRaw( packetHandle );
        AfdxReleasePacket( packetHandle );
      }
    }
  }
}
```

[See Also](javascript:void(0);)