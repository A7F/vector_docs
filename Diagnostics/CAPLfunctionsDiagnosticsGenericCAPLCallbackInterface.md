[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/CAPLfunctionsDiagnosticsGenericCAPLCallbackInterface.md)

**CAPL Functions** » [Diagnostics](CAPLfunctionsDiagnosticsOverview.md) » Generic CAPL Callback Interface

# Diagnostics: Generic CAPL Callback Interface

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

With CANoe 5.1 SP2 an updated CAPL callback interface is available that makes no assumptions of the used transport protocol and supports connection oriented and segmented transmissions easier.

## Interface Configuration

It is now possible, with two (ECU simulations) or three functions (test simulations or test modules) to extensively configure the TP layer. To do this, the `DiagGetCommParameter` function was introduced, which makes set parameters for a diagnostic description accessible in CAPL programs, whereby the parameter qualifiers are identical for all CDDS and manufacturers.

[Diagnostics: Connection of the Communication Layer](CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md)

- Technical References are only available in English

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)