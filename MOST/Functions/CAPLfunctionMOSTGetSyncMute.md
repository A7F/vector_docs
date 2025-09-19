[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetSyncMute.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetSyncMute

# mostGetSyncMute

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostGetSyncMute(long channel, long device);
```

## Description

Returns the mute status of the audio input or output.

## Parameters

- **channel**: Channel of the connected interface.
- **device**:
  - 0: Line-In
  - 1: Line-Out
  - 2: S/PDIF In (VN2640 only)
  - 3: S/PDIF Out (VN2640 only)

## Return Values

- **0**: mute off
- **1**: mute on
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetSyncAudio](CAPLfunctionMOSTSetSyncAudio.md) • [mostSetSyncVolume](CAPLfunctionMOSTSetSyncVolume.md) • [mostSetSyncMute](CAPLfunctionMOSTSetSyncMute.md) • [mostGetSyncVolume](CAPLfunctionMOSTGetSyncVolume.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
