[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetSyncAudio.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetSyncAudio

# mostSetSyncAudio

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostSetSyncAudio(long channel, long channels[4], long device, long mode); // form 1`
- **MOST50 / MOST150**: `long mostSetSyncAudio(long channel, long label, long width, long device, long mode); // form 2`

## Description

The function programs the routing engine for the audio input or output of the network interface. The functions work independently of whether the synchronous channels are reserved. The user must ensure the reservation, e.g., by sending an Alloc message to the timing master.

**MOST50 / MOST150**: The function performs the routing of audio input or output of the network interface. At completion of the routing operation, the event procedure [OnMostSyncAudio()](../EventProcedures/CAPLfunctionOnMOSTSyncAudio.md) will be called.

**Note**: `mostSetSyncAudio` automatically allocates new channels to which Line-In is routed. (Device==0). This function is only available if the connected network interface has its bypass opened.

## Parameters

- **channel**: Channel of the connected interface
- **channels**:
  - `device = 0`: Synchronous channels on which the Line input signal should be routed to.
  - `device = 1`: Synchronous channels from which the data should be routed to the Line output.
  
  The transferred array must always have four entries. Unused channels must be assigned **0xF8**. The four channels have the following mapping to the audio data:
  - `channels[0]`: MSB left audio channel
  - `channels[1]`: LSB left audio channel
  - `channels[2]`: MSB right audio channel
  - `channels[3]`: LSB right audio channel

  **Note**: This parameter is ignored in case the routing is canceled (mode==0).

- **device**:
  - `0`: Line-In: Audio input signals are put on synchronous channels.
  - `1`: Line-Out: Synchronous channel signals are grabbed for audio output.

- **mode**:
  - `0`: Cancels the routing.
  - `1`: Executes the routing.

- **label**: Connection label. In case of Line-In routing (device=0; mode=1) the label parameter has no meaning.

- **width**: Number of channels to be routed.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

See [MOST Access to Analog Audio Channels (Line In/ Headphone Out)](../../../CANoeCANalyzer/MOST/MOSTSynchronousChannelAnalogAudio.md).

**Related Functions**:
- [mostGetChannel](CAPLfunctionMOSTGetChannel.md)
- [mostSyncAlloc](CAPLfunctionMOSTSyncAlloc.md)
- [mostSyncDealloc](CAPLfunctionMOSTSyncDealloc.md)
- [mostSetSyncVolume](CAPLfunctionMOSTSetSyncVolume.md)
- [mostSetSyncMute](CAPLfunctionMOSTSetSyncMute.md)
- [mostGetSyncVolume](CAPLfunctionMOSTGetSyncVolume.md)
- [mostGetSyncMute](CAPLfunctionMOSTGetSyncMute.md)
- [mostSetSyncSpdif](CAPLfunctionMOSTSetSyncSpdif.md)
