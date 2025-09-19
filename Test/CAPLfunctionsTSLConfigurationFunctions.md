[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTSLConfigurationFunctions.md)

**CAPL Functions** » [Test Service Library](CAPLfunctionsTSLOverview.md) » Configuration Functions

# Test Service Library: Configuration Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

The functions [ChkConfig_Init](Functions/CAPLfunctionChkConfigInit.md) and [ChkConfig_SetPrecision](Functions/CAPLfunctionChkConfigSetPrecision.md) permit node-wide configuration of the TestServiceLibrary.

If the TSL is to be used in Simulation Nodes (**not CAPL test modules!**), the initialization function [ChkConfig_Init](Functions/CAPLfunctionChkConfigInit.md) should be called. With this function behavior of the TSL in error cases can also be configured there in roughly outlined steps.

The time base of the TSL can be modified for the node in question.

The function [ChkConfig_SetTitle](Functions/CAPLfunctionChkConfigSetTitle.md) permits the configuration of a check.

## Functions

- **[ChkConfig_DisablePDULayer](Functions/CAPLfunctionChkConfigDisablePDULayer.md)**: Disables the PDU layer for the current bus context.
- **[ChkConfig_EnablePDULayer](Functions/CAPLfunctionChkConfigEnablePDULayer.md)**: Enables the PDU layer for the current bus context.
- **[ChkConfig_Init](Functions/CAPLfunctionChkConfigInit.md)**: Initializes TSL to be used subsequently.
- **[ChkConfig_SetCallback](Functions/CAPLfunctionChkConfigSetCallback.md)**: Sets a CAPL callback for the check.
- **[ChkConfig_SetPDUIDFormat](Functions/CAPLfunctionChkConfigSetPDUIDFormat.md)**: Sets the format of the header ID for the current bus context.
- **[ChkConfig_SetPrecision](Functions/CAPLfunctionChkConfigSetPrecision.md)**: Configures the TSL time basis for the current node.
- **[ChkConfig_SetTitle](Functions/CAPLfunctionChkConfigSetTitle.md)**: Sets the title of a check.

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
