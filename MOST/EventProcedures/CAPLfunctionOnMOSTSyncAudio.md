[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTSyncAudio.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostSyncAudio

# OnMostSyncAudio

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`OnMostSyncAudio(long label, long device, long mode);`

## Description

The event procedure `OnMostSyncAudio` will be called after routing of audio input or output of the network interface (see [mostSetSyncAudio](../Functions/CAPLfunctionMOSTSetSyncAudio.md)).

## Parameters

- **label**: Connection label.
- **device**:
  - 0: Line-In: Audio input signals are put on synchronous channels.
  - 1: Line-Out: Synchronous channel signals are grabbed for audio output.
- **mode**:
  - 0: Routing canceled.
  - 1: Routing executed.

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
