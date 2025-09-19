[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTSLToggleStimulus.md)

**CAPL Functions** » **Test Service Library** » **Stimulus Generator: Toggle Between Two Values**

# Stimulus Generator: Toggle Between Two Values

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

This Stimulus Generator toggles the data sink (signal or environment variable) periodically between two values. These two values are user-defined (Values **A** and **B**) or they are taken directly from the database. The [Reset Function](Functions/CAPLfunctionStmControlStartStopResetDestroy.md) causes the data sink to be immediately set to the value **A**. It does not have any effect on the cycle of the Stimulus Generator.

In this special case the cycle time is exactly half as large as the period T of the Generator.

## Functions that create the Stimulus Generator for stimulating signals and environment/system variables

- [StmCreate_Toggle](Functions/CAPLfunctionStmCreateToggleDatabase.md) (limits taken from database)
- [StmCreate_Toggle](Functions/CAPLfunctionStmCreateToggleUserDefined.md) (limits user-defined)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
