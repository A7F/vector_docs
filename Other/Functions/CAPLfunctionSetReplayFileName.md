# SetReplayFileName

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**: If the function is used in [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md) or CANoe4SW Server Edition, the replay file must be added to the [User Files](../../../CANoeCANalyzer/Ribbon/File/Options/Extensions/ExtensionsUserFiles.md).

## Function Syntax

```
dword setReplayFileName(char nameOfReplayBlock[], char fileName[], char fileType[]);
```

## Description

Replaces the source file of an existing Replay Block. The function call temporarily stops the replay and restarts the Replay Block with the new source file.

The function call temporarily stops the replay and restarts the Replay Block with the new source file, if replay is active before file change.

The function call will not modify the configuration of the Reply block in the [Simulation Setup](../../../CANoeCANalyzer/Windows/SimulationSetup/SimulationSetupWindow.md). The new file will not be stored when saving the configuration.

If you change the source file during measurement in the configuration dialog of the Reply block, the new filename will be stored in the configuration.

**Note**: If the function is executed in the **on start** handler, no replay is started. To start the replay together with the function, the function must be executed outside the **on start** handler. Alternatively, the replay can be started with [ReplayStart](CAPLfunctionReplayStart.md).

## Parameters

- **nameOfReplayBlock**: Contents of the **Replay name** field in the replay configuration dialog.
- **fileName**: The new source file (as absolute or relative path to the configuration file).
- **fileType**: The source file type (as string): ASC, BLF. For all other source file types that are available in the selection dialog of the CANoe DE product Replay Block, use BLF as **fileType** parameter.

## Return Values

—

## Example

```plaintext
SetReplayFilename("R", "replay_test_capl1.asc", "asc");
SetReplayFilename("R", "replay_test_capl1.blf", "blf");
SetReplayFilename("R", "replay_test_capl1.mf4", "blf");
```
