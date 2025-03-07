[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTSLStimulusEV.md)

[CAPL Functions](../CAPLfunctions.md) » [Test Service Library](CAPLfunctionsTSLStimulusOverview.md) » Stimulus Generator: Environment variable as Data Source

# Stimulus Generator: Environment variable as Data Source

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

This Generator offers the option of setting any desired time characteristic for the data sink.

After the start of the Stimulus Generator the data sink (signal or environment variable) is updated periodically with the momentary value of the environment variable.

The [Reset Function](Functions/CAPLfunctionStmControlStartStopResetDestroy.md) always causes the value of the data sink to be immediately set to zero. It has no effect on the cycle time.

Function to create the Stimulus Generator: [StmCreate_EnvVar](Functions/CAPLfunctionStmCreateEnvVar.md)

•  Technical References are only available in English

2024-10-8T21:20:34

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)