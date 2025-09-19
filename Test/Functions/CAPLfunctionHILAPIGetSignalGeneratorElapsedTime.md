[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionHILAPIGetSignalGeneratorElapsedTime.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Stimulus Functions](../CAPLfunctionsTSLStimulusOverview.md) » HILAPIGetSignalGeneratorElapsedTime

# HILAPIGetSignalGeneratorElapsedTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
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

```plaintext
double time;
time = HILAPIGetSignalGeneratorElaspedTime(hGenerator);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
