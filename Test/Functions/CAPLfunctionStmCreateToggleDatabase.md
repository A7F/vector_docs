# StmCreate_Toggle (limits taken from database)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

To stimulate signals:

```
dword StmCreate_Toggle(message aMessage, dbsignal aDBSignal, dword CycleTime);
```

To stimulate signals with the Interaction Layer (IL):

```
dword StmCreate_Toggle(signal aDBSignal, dword CycleTime);
```

To stimulate environment variables:

```
dword StmCreate_Toggle(dbenvvar EnvVarHandle, dword CycleTime);
```

To stimulate system variables:

```
dword StmCreate_Toggle(sysvar SystemVariable, dword CycleTime);
```

## Constructor

[TestStimulus::CreateToggle](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
TestStimulus::CreateToggle(message aMessage, dbsignal aDBSignal, dword CycleTime);
TestStimulus::CreateToggle(signal aDBSignal, dword CycleTime);
TestStimulus::CreateToggle(dbenvvar EnvVarHandle, dword CycleTime);
TestStimulus::CreateToggle(sysvar SystemVariable, dword CycleTime);
```

## Description

Creates a stimulus generator that toggles between two values.

## Parameters

- **aMessage**: Must exist in DB
- **aDBSignal**: Must exist in DB
- **EnvVarHandle**: Must exist in DB
- **SystemVariable**: Must be available in the configuration.
- **CycleTime**: ms; 1 \< x \< ∞
  - Defines the cycle in which the signal value in the message buffer is being updated. There is no affect to the bus.
  - Defines the cycle in which the value of the environment or system variable is being updated.

## Return Values

- **0**: Stimulus could not be created and must not be referenced
- **\> 0**: Stimulus was created successfully and may be referenced using the handle

Later this ID can be used to control the stimuli.

## Example

To stimulate signals:

```c
mId = StmCreate_Toggle(MsgBuf, Msg::Sig, CycleTime);
```

To stimulate signals with the Interaction Layer:

```c
mId = StmCreate_Toggle(Msg::Sig, CycleTime);
```

To stimulate environment variables:

```c
mId = StmCreate_Toggle(EnvVarToStimulate, CycleTime);
```

To stimulate system variables:

```c
mId = StmCreate_Toggle(SysVarToStimulate, CycleTime);
```
