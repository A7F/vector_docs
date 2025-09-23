# HILAPIGetSignalGeneratorElapsedTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
double HILAPIGetSignalGeneratorElaspedTime(dword handle);
```

## Description

Returns the elapsed time of a Signal Generator.

## Parameters

- **handle**: The handle of the Signal Generator.

## Return Values

- **0**: The handle of the Signal Generator is not valid. Note: If the Signal Generator has not been started at the time of this call 0 is returned as well.
- The elapsed time of the Signal Generator in seconds

## Example

Gets the elapsed time of the Signal Generator:

```c
double time;
time = HILAPIGetSignalGeneratorElaspedTime(hGenerator);
```
