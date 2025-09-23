# StmCreate_Ramp (limits taken from database)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

To stimulate signals:

```
dword StmCreate_Ramp(message aMessage, dbsignal aDBSignal, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow);
```

To stimulate signals with the Interaction Layer (IL):

```
dword StmCreate_Ramp(signal aDBSignal, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow);
```

To stimulate environment variables:

```
dword StmCreate_Ramp(dbenvvar EnvVarHandle, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow);
```

To stimulate system variables:

```
dword StmCreate_Ramp(sysvar SystemVariable, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow);
```

## Constructor

[TestStimulus::CreateRamp](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
TestStimulus::CreateRamp(message aMessage, dbsignal aDBSignal, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow);
```

```
TestStimulus::CreateRamp(signal aDBSignal, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow);
```

```
TestStimulus::CreateRamp(dbenvvar EnvVarHandle, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow);
```

```
TestStimulus::CreateRamp(sysvar SystemVariable, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow);
```

## Description

Creates a stimulus generator that creates a ramp.

## Parameters

- **aMessage**: Existing message (dbMsg type) in DB
- **aDBSignal**: Existing signal (dbSignal type) in DB
- **EnvVarHandle**: Existing environment variable (EnvVar type) in DB
- **SystemVariable**: Must be available in the configuration.
- **CycleTime**: ms; 1 \< x \< ∞. Defines the cycle in which the signal value in the message buffer is being updated. There is no affect to the bus. Defines the cycle in which the value of the environment or system variable is being updated.
- **TimeUp**: ms; 0 \< x \< ∞. [Note: For more information please see Stimulus Generator: Creating a Ramp.](../CAPLfunctionsTSLRampStimulus.md)
- **TimeHigh**: ms; 0 \< x \< ∞. [Note: For more information please see Stimulus Generator: Creating a Ramp.](../CAPLfunctionsTSLRampStimulus.md)
- **TimeDown**: ms; 0 \< x \< ∞. [Note: Time Up = Time High = Time Down = 0: ESE Invalid stimuli effect (measurement stops). For more information please see Stimulus Generator: Creating a Ramp.](../CAPLfunctionsTSLRampStimulus.md)
- **TimeLow**: ms; 0 \< x \< ∞. [Note: For more information please see Stimulus Generator: Creating a Ramp.](../CAPLfunctionsTSLRampStimulus.md)

## Return Values

- **0**: Stimulus could not be created and must not be referenced
- **\> 0**: Stimulus was created successfully and may be referenced using the handle

Later this ID can be used to control the stimuli.

## Example

To stimulate signals:

```c
mId = StmCreate_Ramp(MsgBuf, Msg::Sig, CycleTime, Tup, Thigh, Tdown, Tlow);
```

To stimulate signals with the Interaction Layer:

```c
mId = StmCreate_Ramp(Msg::Sig, CycleTime, Tup, Thigh, Tdown, Tlow);
```

To stimulate environment variables:

```c
mId = StmCreate_Ramp(EnvVarToStimulate, CycleTime, Tup, Thigh, Tdown, Tlow);
```

To stimulate system variables:

```c
mId = StmCreate_Ramp(SysVarToStimulate, CycleTime, Tup, Thigh, Tdown, Tlow);
```

[Stimulus Generator: Sample Code StmCreate_Ramp](../CAPLfunctionsTSLSampleCode.md)
