[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetReplayFileNameAndTimeInterval.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » SetReplayFileNameAndTimeInterval

# SetReplayFileNameAndTimeInterval

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
If the function is used in [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md) or CANoe4SW Server Edition, the replay file must be added to the [User Files](../../../CANoeCANalyzer/Ribbon/File/Options/Extensions/ExtensionsUserFiles.md).

## Function Syntax

```plaintext
dword setReplayFileNameAndTimeInterval(char nameOfReplayBlock[], char fileName[], char fileType[], int64 startTime); // form 1
dword setReplayFileNameAndTimeInterval(char nameOfReplayBlock[], char fileName[], char fileType[], int64 startTime, int64 endTime); // form 2
```

## Description

Replaces the source file of an existing Replay Block and allows to set a start and stop time of the recorded events.

The function call temporarily stops the replay and restarts the Replay Block with the new source file, if replay is active before file change.

The function call will not modify the configuration of the Reply Block in the [Simulation Setup](../../../CANoeCANalyzer/Windows/SimulationSetup/SimulationSetupWindow.md). The new file will not be stored when saving the configuration.

If you change the source file during measurement in the configuration dialog of the Reply Block, the new filename will be stored in the configuration.

**Note:** The behavior depends on the settings of the Replay Block. If the replay should be started via CAPL the function [ReplayStart](CAPLfunctionReplayStart.md) has to be used. If the function is used during an active replay, the loading time of the file leads to a delay.

## Parameters

- **nameOfReplayBlock**  
  Contents of the **Replay name** field in the replay configuration dialog.

- **fileName**  
  The new source file (as absolute or relative path to the configuration file).

- **fileType**  
  The source file type (as string): ASC, BLF  
  For all other source file types that are available in the selection dialog of the CANoe DE product Replay Block, use BLF as **fileType** parameter.

- **startTime**  
  Start time of the recorded events in the log file in nano seconds. Use [ConvertTimestampToNS](CAPLfunctionConvertTimestampToNS.md) to convert a timestamp given in days, hours, minutes or seconds.

- **endTime**  
  End time of the recorded events in the log file in nano seconds. Use [ConvertTimestampToNS](CAPLfunctionConvertTimestampToNS.md) to convert a timestamp given in days, hours, minutes or seconds.

## Return Values

—

## Example

```plaintext
variables
{
  char  fileNameBlf[50] = "C:\\anyFolder\\LogFile.blf";
  char  fileNameMf4[50] = "C:\\anyFolder\\LogFile.mf4";
  char  fileNameAsc[50] = "C:\\anyFolder\\LogFile.asc";
}

on preStart
{
  setReplayFileNameAndTimeInterval("ReplayBlockBlf", fileNameBlf, "blf", 5000000000, 10000000000);
  setReplayFileNameAndTimeInterval("ReplayBlockMf4", fileNameMf4, "blf", 2000000000, 50000000000);
  setReplayFileNameAndTimeInterval("ReplayBlockAsc", fileNameAsc, "asc", 1000000000, 7000000000);
}

on key 'a'
{
  replayStart("ReplayBlockBlf");
}

on key 'b'
{
  replayStart("ReplayBlockMf4");
}

on key 'c'
{
  replayStart("ReplayBlockAsc");
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
