[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTSLOverview.md)

[CAPL Functions](../CAPLfunctions.md) » Test Service Library Functions

# Test Service Library Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Functions

- [Types of functions](CAPLfunctionsTSLFunctionTypes.md)
  - Check functions shall be identifiable easily. So the functions are to be prefixed.

- [Status Report functions](CAPLfunctionsTSLStatusReportFunctions.md)
  - In order to query information about a check, generic and check specific status report functions are implemented.

- [Stimulus functions](CAPLfunctionsTSLStimulusOverview.md)
  - Stimulus Generators allow the user to stimulate signals or environment variables - referred to as data sinks in the following - according to a specific time behavior.

- [Check overview](CAPLfunctionsTSLCheckOverview.md)
  - Each function specification `ChkStart_` implies a specification of a `ChkCreate_` function. This `ChkStart_` function creates and additionally starts the check.

- [Commands to control checks](CAPLfunctionsTSLCheckControlCommands.md)
  - These functions can be used to turn off checking in not relevant time, and to continue checking. The control functions can also be used to setup dependencies between checks.

- [Configuration Functions](CAPLfunctionsTSLConfigurationFunctions.md)
  - The `ChkConfig*` functions permit configuration of the TestServiceLibrary.

- [Error codes](CAPLfunctionsTSLErrorCodes.md)
  - For all status report functions, the return values and raised error classes are applied.

[Test Functionality](../../CANoeCANalyzer/Test/TestFeatures.md) • [Test Concept](../../CANoeCANalyzer/Test/TestConcept.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)