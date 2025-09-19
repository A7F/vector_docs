# CarMaker_StartCommand

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CarMaker_StartCommand(char host[char command[]);
```

## Description

Asynchronously calls a generic command and ignores the result.

## Parameters

- **command**: CarMaker script command including parameters.

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
// stop test series after the current TestRun has ﬁnished
gErrorState = CarMaker_StartCommand("TestMgr stop");
```
