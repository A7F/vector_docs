[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionHILAPIStartSignalGenerator.md)

**CAPL Functions** » **Test Service Library** » **Stimulus Functions** » **HILAPIStartSignalGenerator**

# HILAPIStartSignalGenerator

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`dword HILAPIStartSignalGenerator(dword handle);`

## Description

Starts or resumes a Signal Generator.

## Parameters

- **handle**: The handle of the Signal Generator.

## Return Values

- **0**: The handle of the Signal Generator is not valid
- **!=0**: The Signal Generator was started (or resumed)

## Example

Starts or resumes the Signal Generator:

```plaintext
HILAPIStartSignalGenerator(hGenerator);
```

[testWaitForHILAPISignalGeneratorFinished](CAPLfunctionTestWaitForHILAPISignalGeneratorFinished.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
