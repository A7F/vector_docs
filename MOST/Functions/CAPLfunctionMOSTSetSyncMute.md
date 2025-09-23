[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetSyncMute.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetSyncMute

# mostSetSyncMute

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostSetSyncMute(long channel, long device, long mute);
```

## Description

Activates or deactivates the audio input or output of the network interface.

## Parameters

- **channel**: Channel of the connected interface
- **device**:
  - `0`: Line-In
  - `1`: Line-Out
  - `2`: S/PDIF In (VN2640 only)
  - `3`: S/PDIF Out (VN2640 only)
- **mute**:
  - `0`: Active (mute off)
  - `1`: Inactive (mute on)

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

See [MOST Access to Analog Audio Channels (Line In/ Headphone Out)](../../../CANoeCANalyzer/MOST/MOSTSynchronousChannelAnalogAudio.md).

**Related Functions:**

- [mostGetChannel](CAPLfunctionMOSTGetChannel.md)
- [mostSetSyncAudio](CAPLfunctionMOSTSetSyncAudio.md)
- [mostSetSyncVolume](CAPLfunctionMOSTSetSyncVolume.md)
- [mostGetSyncVolume](CAPLfunctionMOSTGetSyncVolume.md)
- [mostGetSyncMute](CAPLfunctionMOSTGetSyncMute.md)
