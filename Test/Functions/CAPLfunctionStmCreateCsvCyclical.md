[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionStmCreateCsvCyclical.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Configuration Functions](../CAPLfunctionsTSLConfigurationFunctions.md) » StmCreate_CSV (cyclical)

# StmCreate_CSV (cyclical)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

To stimulate signals:

```
dword StmCreate_CSV(message aMessage, dbsignal aDBSignal, dword CycleTime, const char *aFile);
```

To stimulate signals with the Interaction Layer (IL):

```
dword StmCreate_CSV(signal aDBSignal, dword CycleTime, const char *aFile);
```

To stimulate environment variables:

```
dword StmCreate_CSV(dbenvvar EnvVarHandle, dbsignal aDBSignal, dword CycleTime, const char *aFile);
```

To stimulate system variables:

```
dword StmCreate_CSV(sysvar SystemVariable, dbsignal aDBSignal, dword CycleTime, const char *aFile);
```

## Constructor

[TestStimulus::CreateCSV](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
TestStimulus::CreateCSV(message aMessage, dbsignal aDBSignal, dword CycleTime, const char *aFile);
TestStimulus::CreateCSV(signal aDBSignal, dword CycleTime, const char *aFile);
TestStimulus::CreateCSV(dbenvvar EnvVarHandle, dbsignal aDBSignal, dword CycleTime, const char *aFile);
TestStimulus::CreateCSV(sysvar SystemVariable, dbsignal aDBSignal, dword CycleTime, const char *aFile);
```

## Description

Creates stimulus generator with csv file as data source.

## Parameters

- **aMessage**: Existing message (dbMsg type) in DB.
- **aDBSignal**: Existing signal (dbSignal type) in DB.
- **aFile**: Existing file to set the stimulus variable.  
  If file not exists: EDI Invalid data input (measurement stops)
- **EnvVarHandle**: Existing environment variable (EnvVar type) in DB.
- **SystemVariable**: Existing system variable (sysVar type).
- **CycleTime**: ms; 1 < x < ∞  
  Defines the cycle in which the signal value in the message buffer is being updated. There is no effect to the bus.  
  Defines the cycle in which the value of the environment or system variable is being updated.

## Return Values

- **0**: Stimulus could not be created and must not be referenced
- **>0**: Stimulus was created successfully and may be referenced using the handle

Later this ID can be used to control the stimuli

## Example

```plaintext
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

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)