[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTSLFunctionTypes.md)

[CAPL Functions](../CAPLfunctions.md) » [Test Service Library](CAPLfunctionsTSLOverview.md) » Types of Functions

# Test Service Library: Types of Functions

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

Check functions shall be identifiable easily. So the functions are to be prefixed in the following way:

- ChkCreate /ChkStart_ for check creation and check start functions (see [check descriptions](../../TestCommands/CheckDescriptions.md))
- [ChkControl_](CAPLfunctionsTSLCheckControlCommands.md) for check control functions
- [ChkQuery_](CAPLfunctionsTSLStatusReportFunctions.md) for check result query functions
- [ChkConfig_](CAPLfunctionsTSLConfigurationFunctions.md) for TSL configuration functions

## Function and User Interface

Types of arguments (defined in CAPL) that can be handed over.

- **Network**: Network database symbol (or case sensitive string).
- **Node**: Node database symbol (or case sensitive string).
- **Message**: ID or database symbol of the message to check (or case sensitive string).
- **Signal**: Database symbol of the signal to check, qualified with the message (or case sensitive signal short name).
- **Callback**: Name of the function to call (signature is fixed).
- **Duration**: Length of an interval with the unit of the current precision. (Default: milliseconds)
- **Check**: Reference-ID of a check (type "dword"), returned on check creation.

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
