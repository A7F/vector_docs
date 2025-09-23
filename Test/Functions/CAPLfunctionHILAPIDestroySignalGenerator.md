# HILAPIDestroySignalGenerator

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword HILAPIDestroySignalGenerator(dword handle);
```

## Description

Destroys an instance of a Signal Generator.

## Parameters

- **handle**: The handle of the Signal Generator.

## Return Values

- **0**: The handle of the Signal Generator is not valid
- **!=0**: Successful destruction of the Signal Generator

## Example

Destroys an instance of a ASAM HILAPI Signal Generator:

```c
HILAPIDestroySignalGenerator( hGenerator);
```
