# StartReplayFile

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note:**

- Note that a relative path to the configuration directory or an absolute path can be used to specify the replay file. Just the filename of the replay file can also be specified. For this option, the replay file must be located in the same folder as the configuration.
- If the function is used in [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md) or CANoe4SW Server Edition, the replay file must be added to the [User Files](../../../CANoeCANalyzer/Ribbon/File/Options/Extensions/ExtensionsUserFiles.md).

## Function Syntax

```
dword StartReplayFile(char fileName[]);
```

## Description

Starts playing the replay file with the name **fileName**.

This function replays events of the following types:

- CAN messages
- CAN Error Frames
- CAN overload frames (not sent, only visible in Measurement Setup)
- J1708 messages
- Ethernet packets
- WLAN packets
- AFDX packets
- Diagnostic requests
- GPS events
- Signal values
- System variable updates
- Environment variable updates

In particular, replay of LIN, FlexRay, and MOST events using this function is not possible.

All events are replayed on the same channel as they are recorded in the replay file. Events targeted to non-configured channels are discarded.

The first event in the replay file is replayed immediately, disregarding its time stamp.

The start of replay is timely decoupled from calling this function, so replay will actually start a short but indeterminate time span after this function returns.

## Parameters

- **fileName**: Replay file.

## Return Values

The returned handle is required to [stop the replay file](CAPLfunctionStopReplayFile.md).

## Example

—
