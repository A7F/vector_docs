[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionHILAPIGetSignalGeneratorState.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Stimulus Functions](../CAPLfunctionsTSLStimulusOverview.md) » HILAPIGetSignalGeneratorState

# HILAPIGetSignalGeneratorState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword HILAPIGetSignalGeneratorState(dword handle);
```

## Description

Returns the state of a Signal Generator.

## Parameters

- **handle**: The handle of the Signal Generator.

## Return Values

- **0**: The handle of the Signal Generator is not valid
- **1**: The Signal Generator is in the state READY
- **2**: The Signal Generator is in the state FINISHED
- **3**: The Signal Generator is in the state PAUSED
- **4**: The Signal Generator is in the state RUNNING
- **5**: The Signal Generator is in the state STOPPED

## Example

Gets the state of the Signal Generator:

```c
dword state;
state = HILAPIGetSignalGeneratorState(hGenerator);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
