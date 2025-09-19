[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionHILAPICreateSignalGenerator.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Stimulus Functions](../CAPLfunctionsTSLStimulusOverview.md) » HILAPICreateSignalGenerator

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

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
