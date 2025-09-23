[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetSyncVolume.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetSyncVolume

# mostSetSyncVolume

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostSetSyncVolume(long channel, long device, long volume);
```

## Description

Sets the volume of the audio input or output of the network interface.

## Parameters

- **channel**: Channel of the connected interface
- **device**:
  - `0`: Line-In
  - `1`: Line-Out
- **volume**: Value range: 0...255 (0...100%)

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

See [MOST Access to Analog Audio Channels (Line In/ Headphone Out)](../../../CANoeCANalyzer/MOST/MOSTSynchronousChannelAnalogAudio.md).

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetSyncAudio](CAPLfunctionMOSTSetSyncAudio.md) • [mostSetSyncMute](CAPLfunctionMOSTSetSyncMute.md) • [mostGetSyncVolume](CAPLfunctionMOSTGetSyncVolume.md) • [mostGetSyncMute](CAPLfunctionMOSTGetSyncMute.md)
