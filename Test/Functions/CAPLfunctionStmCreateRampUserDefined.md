[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionStmCreateRampUserDefined.md)

# StmCreate_Ramp (limits user-defined)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Stimulus Functions](../CAPLfunctionsTSLStimulusOverview.md) » StmCreate_Ramp (limits user-defined)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

To stimulate signals:

```
dword StmCreate_Ramp(message aMessage, dbsignal aDBSignal, double ValueA, double ValueB, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow); // form 1
```

To stimulate signals with the Interaction Layer (IL):

```
dword StmCreate_Ramp(signal aDBSignal, double ValueA, double ValueB, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow); // form 2
```

To stimulate environment variables:

```
dword StmCreate_Ramp(dbenvvar EnvVarHandle, double ValueA, double ValueB, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow); // form 3
```

To stimulate system variables:

```
dword StmCreate_Ramp(sysvar SystemVariable, double ValueA, double ValueB, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow); // form 4
```

To stimulate system variables (64 bit):

```
dword StmCreate_Ramp(sysvar SystemVariable, int64 ValueA, int64 ValueB, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow); // form 5
```

## Constructor

[Constructor](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
TestStimulus::CreateRamp(message aMessage, dbsignal aDBSignal, double ValueA, double ValueB, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow); // form 1
```

```
TestStimulus::CreateRamp(signal aDBSignal, double ValueA, double ValueB, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword long TimeLow); // form 2
```

```
TestStimulus::CreateRamp(dbenvvar EnvVarHandle, double ValueA, double ValueB, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow); // form 3
```

```
TestStimulus::CreateRamp(sysvar SystemVariable, double ValueA, double ValueB, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow); // form 4
```

```
TestStimulus::CreateRamp(sysvar SystemVariable, int64 ValueA, int64 ValueB, dword CycleTime, dword TimeUp, dword TimeHigh, dword TimeDown, dword TimeLow); // form 5
```

## Description

Creates a stimulus generator that creates a ramp.

## Parameters

- **aMessage**: Existing message (dbMsg type) in DB
- **aDBSignal**: Existing signal (dbSignal type) in DB
- **EnvVarHandle**: Existing environment variable (EnvVar type) in DB
- **SystemVariable**: Must be available in the configuration.
- **ValueA and ValueB**:
  - Value A = Value B: ESE Invalid stimuli effect (measurement stops)
  - Value A and Value B are physical values, not raw values. They can be user-defined or will be taken from the CANdb++ database (dbc-file) that is assigned to the CANoe configuration and are called Minimum and Maximum of the signal.
- **CycleTime**: ms; 1 < x < ∞
  - Defines the cycle in which the signal value in the message buffer is being updated. There is no affect to the bus.
  - Defines the cycle in which the value of the environment or system variable is being updated.
- **TimeUp**: ms; 0 < x < ∞
  - For more information please see [Stimulus Generator: Creating a Ramp](../CAPLfunctionsTSLRampStimulus.md).
- **TimeHigh**: ms; 0 < x < ∞
  - For more information please see [Stimulus Generator: Creating a Ramp](../CAPLfunctionsTSLRampStimulus.md).
- **TimeDown**: ms; 0 < x < ∞
  - Time Up = Time High = Time Down = 0: ESE Invalid stimuli effect (measurement stops)
  - For more information please see [Stimulus Generator: Creating a Ramp](../CAPLfunctionsTSLRampStimulus.md).
- **TimeLow**: ms; 0 < x < ∞
  - For more information please see [Stimulus Generator: Creating a Ramp](../CAPLfunctionsTSLRampStimulus.md).

## Return Values

- **0**: Stimulus could not be created and must not be referenced
- **> 0**: Stimulus was created successfully and may be referenced using the handle

Later this ID can be used to control the stimuli.

## Example

To stimulate signals:

```
mId = StmCreate_Ramp(MsgBuf, Msg::Sig, ValueA, ValueB, CycleTime, Tup, Thigh, Tdown, Tlow);
```

To stimulate signals with the Interaction Layer:

```
mId = StmCreate_Ramp(Msg::Sig, ValueA, ValueB, CycleTime, Tup, Thigh, Tdown, Tlow);
```

To stimulate environment variables:

```
mId = StmCreate_Ramp(EnvVarToStimulate, ValueA, ValueB, CycleTime, Tup, Thigh, Tdown, Tlow);
```

To stimulate system variables:

```
mId = StmCreate_Ramp(SysVarToStimulate, ValueA, ValueB, CycleTime, Tup, Thigh, Tdown, Tlow);
```

### Example Code

```plaintext
variables
{
    message NewMessage aNewMessage;
    mstimer mytimer;
    dword yMin = 0;
    dword yMax = 100;
    dword ramp_cycletime = 50;
    long stm_ramp;
}

on preStart
{
    chkConfig_Init ("user");
    stm_ramp = StmCreate_Ramp(aNewMessage, NewMessage::NewSignal, yMin, yMax, ramp_cycletime, 5000, 100, 0, 0);
}

on start
{
    long ret;
    ret = StmControl_Start(stm_ramp);
    settimer (mytimer, ramp_cycletime);
}

on timer mytimer
{
    if (yMax == aNewMessage.NewSignal) stmControl_Stop (stm_ramp);
    output (aNewMessage);
    settimer (mytimer, ramp_cycletime);
}

on preStop
{
    StmControl_Destroy (stm_ramp);
}
```

```plaintext
variables
{
    sysvar mySysvar;
    mstimer mytimer;
    dword yMin = 0;
    dword yMax = 100;
    dword ramp_cycletime = 50;
    long stm_ramp;
}

on preStart
{
    chkConfig_Init ("user");
    stm_ramp = StmCreate_Ramp(mySysvar, yMin, yMax, ramp_cycletime, 5000, 100, 0, 0);
}

on start
{
    long ret;
    ret = StmControl_Start(stm_ramp);
    settimer (mytimer, ramp_cycletime);
}

on timer mytimer
{
    if (yMax == $mySysvar) stmControl_Stop (stm_ramp);
    //do something with sysvar
    settimer (mytimer, ramp_cycletime);
}

on preStop
{
    StmControl_Destroy (stm_ramp);
}
```

[Stimulus Generator: Sample Code StmCreate_Ramp](../CAPLfunctionsTSLSampleCode.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
