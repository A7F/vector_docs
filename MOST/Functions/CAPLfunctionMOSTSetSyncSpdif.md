[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetSyncSpdif.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetSyncSpdif

# mostSetSyncSpdif

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is available with MOST hardware VN2610, VN2640, OptoLyzer G2 3050e, OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e and OptoLyzer MOCCA compact 150c.

## Function Syntax

```plaintext
long mostSetSyncSpdif(long channel, long channels[8], long device, long mode); // form 1
MOST50 / MOST150: long mostSetSyncSpdif(long channel, long label, long width, long device, long mode); // form 2
```

## Description

The function programs the routing engine for S/PDIF input or output of the network interface. The function works independently of whether the synchronous channels are reserved. The user must ensure the reservation, e.g. by sending an Alloc message to the timing master.

**MOST50 / MOST150**: The function performs the routing of S/PDIF input or output of the network interface. At completion of the routing operation the event procedure [OnMostSyncSpdif()](../EventProcedures/CAPLfunctionOnMOSTSyncSpdif.md) will be called.

**Note**  
`mostSetSyncSpdif` automatically allocates new channels to which the S/PDIF In is routed. (Device==0).  
SPDIF In (device==0) is only available if the connected network interface has its bypass opened.  
Call [mostSetSyncMute](CAPLfunctionMOSTSetSyncMute.md) to mute/demute the signal.

## Parameters

- **channel**: Channel of the connected interface
- **channels**:
  - **S/PDIF In**: Synchronous channels on which the S/PDIF input signal should be routed to.
  - **S/PDIF Out**: Synchronous channels from which the data should be routed to the S/PDIF output.

  The transferred array must always have eight entries. Unused channels must be assigned `0xF8`. The eight channels have the following mapping to the S/PDIF data:
  - channels[0]: MSB left audio channel
  - channels[1]: LSB left audio channel
  - channels[2]: AUX left audio channel
  - channels[3]: VUCP left audio channel
  - channels[4]: MSB right audio channel
  - channels[5]: LSB right audio channel
  - channels[6]: AUX right audio channel
  - channels[7]: VUCP right audio channel

  **Note**  
  This parameter is ignored in case the routing is canceled (mode==0).

- **device**:
  - 0: S/PDIF in: S/PDIF input signals are put on synchronous channels.
  - 1: S/PDIF out: Synchronous channel signals are grabbed for S/PDIF output.

- **mode**:
  - 0: Cancels the routing.
  - 1: Executes the routing.

- **label**: Connection label. In case of S/PDIF-In routing (device=0; mode=1) the label parameter has no meaning.

- **width**: Number of channels to be routed.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

See [MOST Access to Digital Audio Channels (S/PDIF In and Out)](../../../CANoeCANalyzer/MOST/MOSTSynchronousChannelDigitalAudio.md).

[mostSetSyncSpdifLock](CAPLfunctionMOSTSetSyncSpdifLock.md) • [mostSetSyncSpdifMode](CAPLfunctionMOSTSetSyncSpdifMode.md) • [mostGetSyncSpdifMode](CAPLfunctionMOSTGetSyncSpdifMode.md) • [mostSetClockSource](CAPLfunctionMOSTSetClockSource.md) • [mostGetClockSource](CAPLfunctionMOSTGetClockSource.md) • [mostSetSyncAudio](CAPLfunctionMOSTSetSyncAudio.md)
