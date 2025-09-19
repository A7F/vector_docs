[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetSyncVolume.md)

# mostGetSyncVolume

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetSyncVolume

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long mostGetSyncVolume(long channel, long device);
```

## Description

Returns the volume of the audio input or output.

## Parameters

- **channel**: Channel of the connected interface.
- **device**:
  - 0: Line-In
  - 1: Line-Out

## Return Values

- **0...255**: Volume (255 = 100%)
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetSyncAudio](CAPLfunctionMOSTSetSyncAudio.md) • [mostSetSyncVolume](CAPLfunctionMOSTSetSyncVolume.md) • [mostSetSyncMute](CAPLfunctionMOSTSetSyncMute.md) • [mostGetSyncMute](CAPLfunctionMOSTGetSyncMute.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
