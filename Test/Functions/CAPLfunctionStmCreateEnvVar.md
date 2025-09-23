[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionStmCreateEnvVar.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Stimulus Functions](../CAPLfunctionsTSLStimulusOverview.md) » StmCreate_EnvVar

# StmCreate_EnvVar

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

To stimulate signals:

```
dword StmCreate_EnvVar(message aMessage, dbsignal aDBSignal, dbEnvVar aEnvVar, dword CycleTime);
```

To stimulate signals with the Interaction Layer (IL):

```
dword StmCreate_EnvVar(signal aDBSignal, dbEnvVar aEnvVar, dword CycleTime);
```

## Constructor

[Constructor](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
TestStimulus::CreateEnvVar(message aMessage, const dbsignal aDBSignal, dbEnvVar aEnvVar, dword CycleTime);
TestStimulus::CreateEnvVar(const signal aDBSignal, dbEnvVar aEnvVar, dword CycleTime);
```

## Description

Creates the stimulus with environment variables as data source.

## Parameters

- **aMessage**: Must exist in DB
- **aDBSignal**: Must exist in DB
- **aEnvVar**: Must exist in DB
- **CycleTime**: ms; 1 < x < ∞  
  Defines the cycle in which the signal value in the message buffer is being updated. There is no affect to the bus.

## Return Values

- **0**: Stimulus could not be created and must not be referenced
- **> 0**: Stimulus was created successfully and may be referenced using the handle

Later this ID can be used to control the stimuli.

## Example

To stimulate signals:

```
mId = StmCreate_EnvVar(MsgBuf, Msg::Sig, EnvVar, CycleTime);
```

To stimulate signals with the Interaction Layer:

```
mId = StmCreate_EnvVar(Msg::Sig, EnvVar, CycleTime);
```
