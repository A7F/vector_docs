[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTSLRampStimulus.md)

# Stimulus Generator: Creating a Ramp

[CAPL Functions](../CAPLfunctions.md) » [Test Service Library](CAPLfunctionsTSLStimulusOverview.md) » Stimulus Generator: Creating a Ramp

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

This Stimulus Generator generates a ramp. After the start, the Stimulus Generator updates the data sink (signal or environment variable) periodically. Value **A** and value **B** describe the upper and lower limits of the ramp, respectively. The [Reset Function](Functions/CAPLfunctionStmControlStartStopResetDestroy.md) of the Generator can be used either after a Generator stop or while it is operating. In both cases, the [Reset Function](Functions/CAPLfunctionStmControlStartStopResetDestroy.md) causes the value of the data sink to immediately assume value **A** and the ramp begins anew. The Reset Function has no effect on the cycle time.

**Note**: At least Time Up, Time High, or Time Down have to be set to a value > 0. If check failed, the measurement will be stopped.

## Functions that create the Stimulus Generator for stimulating signals and environment/system variables

- [StmCreate_Ramp](Functions/CAPLfunctionStmCreateRampDatabase.md) (limits taken from database)
- [StmCreate_Ramp](Functions/CAPLfunctionStmCreateRampUserDefined.md) (limits user-defined)

[Stimulus Generator: Sample Code StmCreate_Ramp](CAPLfunctionsTSLSampleCode.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)