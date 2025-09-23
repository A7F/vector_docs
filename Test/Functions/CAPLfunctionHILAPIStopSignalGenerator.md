# HILAPIStopSignalGenerator

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword HILAPIStopSignalGenerator(dword handle);
```

## Description

Stops a Signal Generator.

## Parameters

- **handle**: The handle of the Signal Generator.

## Return Values

- **0**: The handle of the Signal Generator is not valid
- **!=0**: The Signal Generator was stopped

## Example

Stops the Signal Generator:

```
HILAPIStopSignalGenerator( hGenerator);
```
