# StmCreate_CSV (non-cyclical)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

**To stimulate signals:**

```c
dword StmCreate_CSV(message aMessage, dbsignal aDBSignal, const char *aFile);
```

**To stimulate signals with the Interaction Layer (IL):**

```c
dword StmCreate_CSV(signal aDBSignal, const char *aFile);
```

**To stimulate environment variables:**

```c
dword StmCreate_CSV(dbenvvar EnvVarHandle, dbsignal aDBSignal, const char *aFile);
```

**To stimulate system variables:**

```c
dword StmCreate_CSV(sysvar SystemVariable, dbsignal aDBSignal, const char *aFile);
```

## Constructor

[TestStimulus::CreateCSV](../../../Shared/CAPL/General/ClassesAndObjects.md)

```c
TestStimulus::CreateCSV(message aMessage, dbsignal aDBSignal, const char *aFile);
TestStimulus::CreateCSV(signal aDBSignal, const char *aFile);
TestStimulus::CreateCSV(dbenvvar EnvVarHandle, dbsignal aDBSignal, const char *aFile);
TestStimulus::CreateCSV(sysvar SystemVariable, dbsignal aDBSignal, const char *aFile);
```

## Description

Creates stimulus generator with csv file as data source.

## Parameters

- **aMessage**: Existing message (dbMsg type) in DB.
- **aDBSignal**: Existing signal (dbSignal type) in DB.
- **aFile**: Existing file to set the stimulus variable. If file not exists: EDI Invalid data input (measurement stops)
- **EnvVarHandle**: Existing environment variable (EnvVar type) in DB.
- **SystemVariable**: Existing system variable (sysVar type).

## Return Values

- **0**: Stimulus could not be created and must not be referenced
- **\> 0**: Stimulus was created successfully and may be referenced using the handle

Later this ID can be used to control the stimuli.

## Example

```c
dword stimId;
dbSignal StimSig;

//Create stimulus for csv files and dbSignal
stimId = StmCreate_CSV(StimSig, "stimulus.csv");

//Start the process of reading the stimulus from csv file
StmControl_Start(stimId);
testWaitForTimeout(2000);

//Destroy the created stimulus
StmControl_Destroy(stimId);

The CSV-file for the CAPL function should look like this:

Time, StimSig
136090,100
146090,-100
156090,100
…
```

[Stimulus Generator: CSV File as Data Source](../CAPLfunctionsTSLStimulusCsvFile.md)
