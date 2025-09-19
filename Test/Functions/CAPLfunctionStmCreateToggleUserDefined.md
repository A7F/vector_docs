[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionStmCreateToggleUserDefined.md)

# StmCreate_Toggle (limits user-defined)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Stimulus Functions](../CAPLfunctionsTSLStimulusOverview.md) » StmCreate_Toggle (limits user-defined)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

To stimulate signals:

`dword StmCreate_Toggle(message aMessage, dbsignal aDBSignal, double ValueA, double ValueB, dword CycleTime); // form 1`

To stimulate signals with the Interaction Layer (IL):

`dword StmCreate_Toggle(signal aDBSignal, double ValueA, double ValueB, dword CycleTime); // form 2`

To stimulate environment variables:

`dword StmCreate_Toggle(dbenvvar EnvVarHandle, double ValueA, double ValueB, dword CycleTime); // form 3`

To stimulate system variables:

`dword StmCreate_Toggle(sysvar SystemVariable, double ValueA, double ValueB, dword CycleTime); // form 4`

To stimulate system variables (64 bit):

`dword StmCreate_Toggle(sysvar SystemVariable, int64 ValueA, double ValueB, int64 CycleTime); // form 5`

## Constructor

[TestStimulus::CreateToggle](../../../Shared/CAPL/General/ClassesAndObjects.md)

`TestStimulus::CreateToggle(message aMessage, dbsignal aDBSignal, double ValueA, double ValueB, dword CycleTime); // form 1`

`TestStimulus::CreateToggle(signal aDBSignal, double ValueA, double ValueB, dword CycleTime); // form 2`

`TestStimulus::CreateToggle(dbenvvar EnvVarHandle, double ValueA, double ValueB, dword CycleTime); // form 3`

`TestStimulus::CreateToggle(sysvar SystemVariable, double ValueA, double ValueB, dword CycleTime); // form 4`

`TestStimulus::CreateToggle(sysvar SystemVariable, int64 ValueA, int64 ValueB, dword CycleTime); // form 5`

## Description

Creates a stimulus generator that toggles between two values.

## Parameters

- **aMessage**: Must exist in DB
- **aDBSignal**: Must exist in DB
- **EnvVarHandle**: Must exist in DB
- **SystemVariable**: Must be available in the configuration.
- **ValueA and ValueB**:
  - Note: Use the **int64 parameters** for system variables of UInt64 and Int64 type to cover the whole value range. The int64 parameter is interpreted for system variables of UInt64 type as qword (uint64).
  - Value A = Value B: ESE Invalid stimuli effect (measurement stops)
  - Value A and Value B are physical values, not raw values. They can be user-defined or will be taken from the CANdb++ database (dbc-file) that is assigned to the CANoe configuration and are called Minimum and Maximum of the signal.
- **CycleTime**: ms; 1 < x < ∞
  - Defines the cycle in which the signal value in the message buffer is being updated. There is no affect to the bus.
  - Defines the cycle in which the value of the environment or system variable is being updated.

## Return Values

- **0**: Stimulus could not be created and must not be referenced
- **> 0**: Stimulus was created successfully and may be referenced using the handle

Later this ID can be used to control the stimuli.

## Example

To stimulate signals:

```plaintext
mId = StmCreate_Toggle(MsgBuf, Msg::Sig, ValueA, ValueB, CycleTime);
```

To stimulate signals with the Interaction Layer:

```plaintext
mId = StmCreate_Toggle(Msg::Sig, ValueA, ValueB, CycleTime);
```

To stimulate environment variables:

```plaintext
mId = StmCreate_Toggle(EnvVarToStimulate, ValueA, ValueB, CycleTime);
```

To stimulate system variables:

```plaintext
mId = StmCreate_Toggle(SysVarToStimulate, ValueA, ValueB, CycleTime);
```

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
