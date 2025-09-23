[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/CAPLfunctionsFileFunctions.md)

**CAPL Functions** » [General](CAPLGeneralStartPage.md) » **File Functions**

# File Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

There is often the need to save variables or measurement values over a period of time covering a number of measurements. File functions are provided in CAPL for this purpose.

While file access operations are generally conceived to be easy to use and reliable they are rather slow. Therefore file access should not be done in time-critical phases during measurement. It is recommended to use CAPL file access mainly in the [on preStart](EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) and `on stop` event handlers.

**Note**

If file functions are used in CAPL programs in the Simulation Setup or test setup and your CANoe DE product is running in [distributed mode](../../CANoeCANalyzer/RTSetup/DistributedMode/DistributedModeConcept.md) or [standalone mode](../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md), it is required to predefine the files to be accessed in advance under **Configuration|Options|Extensions|User Files**. The files on the user computer and on the remote device are synchronized before measurement start and after measurement end.

[File Access CAPL Functions](CAPLfunctionsGeneralOverview.md#FileFunctions) • [File Search Procedure](CAPLfunctionsFileSearchProcedure.md) • [Configuration Requirements](../../CANoeCANalyzer/RTSetup/DistributedMode/DistributedModeConfigRequirements.md)
