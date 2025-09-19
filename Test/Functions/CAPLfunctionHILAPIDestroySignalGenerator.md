[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionHILAPIDestroySignalGenerator.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Stimulus Functions](../CAPLfunctionsTSLStimulusOverview.md) » HILAPIDestroySignalGenerator

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

```plaintext
HILAPIDestroySignalGenerator( hGenerator);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
