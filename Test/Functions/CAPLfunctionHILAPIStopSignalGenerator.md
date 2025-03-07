[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionHILAPIStopSignalGenerator.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Stimulus Functions](../CAPLfunctionsTSLStimulusOverview.md) » HILAPIStopSignalGenerator

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)