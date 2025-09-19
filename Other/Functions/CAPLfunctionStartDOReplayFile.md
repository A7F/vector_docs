[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStartDOReplayFile.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » StartDOReplayFile

# StartDOReplayFile

**Valid for**: [CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**: Note that a relative path to the configuration directory or an absolute path can be used to specify the replay file. Just the filename of the replay file can also be specified. For this option, the replay file must be located in the same folder as the configuration.

## Function Syntax

- `dword StartDOReplayFile (char filename[]); // form 1`
- `dword StartDOReplayFile (char filename[], dword role); // form 2`
- `dword StartDOReplayFile (char filename[], dword role, dword ignoreSubscriptions, dword ignoreAnnouncements); // form 3`
- `dword StartDOReplayFile (char filename[], dword role, dword ignoreSubscriptions, dword ignoreAnnouncements, dword enforceConnection); // form 4`

## Description

Starts replaying a file with [distributed objects](../../../CANoeCANalyzer/CommunicationConcept/CCDistributedObjects.md) named **fileName**.

## Parameters

- **filename**: Filename of the file to be replayed.
- **role**: Role to be replayed.
  - `0x0`: Provider + Consumer (default)
  - `0x1`: Provider
  - `0x2`: Consumer
- **ignoreSubscriptions**: If set, subscriptions are ignored.
  - `0x0`: Send subscriptions (default)
  - `0x1`: Subscriptions are ignored
- **ignoreAnnouncements**: If set, announcements are ignored.
  - `0x0`: Send announcements (default)
  - `0x1`: Announcements are ignored
- **enforceConnection**: Enables enforcing connections between participants via the first virtual network.
  - `0x0`: Uses the settings from the data model (default)
  - `0x1`: Enforces a connection between participants

## Return Values

The returned handle is required to [stop the replay file](CAPLfunctionStopReplayFile.md).

## Example

—

[StartReplayFile](CAPLfunctionStartReplayFile.md) | [StopReplayFile](CAPLfunctionStopReplayFile.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
