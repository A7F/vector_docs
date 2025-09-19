[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxInitPacket.md)

## CAPL Functions » AFDX » AfdxInitPacket

### Function Syntax

- `long AfdxInitPacket( long msgID, char msgName[], long initSignals ); // form 1`
- `long AfdxInitPacket( long srcIP, long dstIP, long srcUdpPort, long dstUdpPort, long virtualLinkId, long payloadSize ); // form 2`
- `long AfdxInitPacket( long copyFromPacket ); // form 3`
- `long AfdxInitPacket( ); // form 4`
- `long AfdxInitPacket( long rawDataLength, byte rawData[] ); // form 5`
- `long AfdxInitPacket( long rawDataLength, char rawData[] ); // form 6`
- `long AfdxInitPacket( long rawDataLength, struct * rawData ); // form 7`

### Description

Any access to an AFDX message requires a valid handle. This function returns such a handle and enables the user to manipulate or transmit the message in subsequent calls to [AFDX CAPL functions](../CAPLfunctionsAFDXOverview.md). This function allocates internal buffer memory and initializes the corresponding protocol fields. The level of initialization depends on the selected function signature.

- **Form 1**: When an [AFDX DBC](../../../CANoeCANalyzer/AFDX/procedures/afdxGenerateDbc.md) is used, this function may be called for a message in this DBC with either the message ID or the message name. Note that the message attributes from the DBC file are used for initialization too.
- **Form 2**: When the complete addressing information is available, this function signature provides a convenient way to create the handle.
- **Form 3**: If you want to create another instance of an existing AFDX message (either previously created with `AfdxInitPacket` or signaled with the callback `<OnAfdxPacket>`), this function signature should be used. Addressing information, attributes, and payload contents are duplicated for the new handle.
- **Form 4**: This function signature returns a handle to an "empty" message (all fields are set to "0").
- **Form 5-7**: With these function signatures, it is possible to create a message based on either a raw byte stream or an initialized structure. The specified initialization data is copied to the target message "as is".

### Parameters

- **msgID**
  - `0`: Instead of `msgID`, the parameter `msgName` is used for referencing the message in the assigned AFDX DBC file.
  - `!0`: This value references a message ID in the assigned AFDX DBC file. The corresponding message is used for initialization.

- **msgName**
  - `0`: Instead of `msgName`, the parameter `msgID` is used for referencing the message in the assigned AFDX DBC file.
  - `<Message Name>`: This value references a message name in the assigned AFDX DBC file. The corresponding message is used for initialization.

- **initSignals**
  - `0`: The signal area of the message is initialized with 0.
  - `!0`: The value of an already initialized signal is used.

- **srcIP**: Source IP address.

- **dstIP**: Destination IP address. The [IP address](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolAfdx.md) is given as an integer value (hexadecimal address notation 0xwwxxyyzz corresponds to WW.XX.YY.ZZ with decimal notation). For this function, the value of the source IP address has to start with 10.XX.YY.ZZ. For the destination IP address, the value has to start with either 10.XX.YY.ZZ or 224.XX.YY.ZZ. Note that you may enter the IP addresses later on with the function [AfdxSetTokenInt](CAPLfunctionAfdxSetTokenInt.md).

- **srcUdpPort**: `1..65535`: source UDP port

- **dstUdpPort**: `1..65535`: destination UDP port

- **virtualLinkId**: `1..65535`: Virtual Link Identifier

- **payloadSize**: `0..8192`: payload size of AFDX message

- **copyFromPacket**: The protocol header and the data of a message identified via `copyFromPacket` is used for initializing a new message.

- **rawDataLength**: This is the number of bytes in an initialization array or structure. Note that the size may be gathered with [elCount](../../Other/Functions/CAPLfunctionElCount.md) (for byte rawData[]), [strlen](../../Other/Functions/CAPLfunctionStrLen.md) (for char rawData[]) or [__size_of](../../../Shared/CAPL/General/Structures.md) (for struct * rawData).

- **rawData**: Raw initialization data.

### Return Values

- **0**: Could not initialize the message. The [error code](../CAPLfunctionsAFDXErrorCodes.md) may be retrieved with [AfdxGetLastError](CAPLfunctionAfdxGetLastError.md).
- **!0**: Handle of the message.

### Example

**Form 1**

```plaintext
variables
{
  // create packet handle
  long gMSG1;
}

// Snippet placed in e.g. on preStart system function

// instantiate message MSG1
gMSG1 = AfdxInitPacket( 0, "AFDX_MSG_OUT_1", 0 );
if (gMSG1 == 0)
{
  write( "Creating packet failed, result %d", AfdxGetLastError() );
}
```

**Form 2**

```plaintext
variables
{
  // static configuration for message MSG1
  const dword k_MSG1_SrcIP  = 0x0A0A0401; // source IP address = 10.10.4.1
  const dword k_MSG1_DstIP  = 0xE0E03908; // destination IP address = 224.224.57.8
  const dword k_MSG1_SrcUDP = 35420; // source UDP port
  const dword k_MSG1_DstUDP = 35420; // destination UDP port
  const dword k_VLID1       = 14600; // VL ID
  const dword k_MSG1_MxFrSz = 784; // maximum frame size

  // create packet handle
  long gMSG1;
}

// Snippet placed in e.g. on preStart system function

// instantiate packet MSG1
gMSG1 = AfdxInitPacket( k_MSG1_SrcIP, k_MSG1_DstIP, k_MSG1_SrcUDP, k_MSG1_DstUDP, k_VLID1, k_MSG1_MxFrSz );
if (gMSG1 == 0)
{
  write( "Creating packet failed, result %d", AfdxGetLastError() );
}
```

[See Also](javascript:void(0);)
