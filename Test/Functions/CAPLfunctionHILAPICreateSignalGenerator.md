# HILAPICreateSignalGenerator

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword HILAPICreateSignalGenerator(char filename[]);
```

## Description

Creates a Signal Generator from an ASAM HILAPI Signal Generator definition file.

## Parameters

- **filename**: The location of the Signal Generator definition file.

## Return Values

- **0**: The Signal Generator could not be created
- **!=0**: A handle to the created Signal Generator

## Example

Creates a ASAM HILAPI Signal Generator:

```c
dword hGenerator;
hGenerator = HILAPICreateSignalGenerator("mygenerator.sti");
```

[testWaitForHILAPISignalGeneratorLoaded](CAPLfunctionTestWaitForHILAPISignalGeneratorLoaded.md)
