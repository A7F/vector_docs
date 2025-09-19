[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/EventProcedures/CAPLfunctionOnLINDlcInfo.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » on linDlcInfo

# on linDlcInfo

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Description

The event procedure `on linDlcInfo` is called when the LIN hardware has successfully measured the length of an unknown frame. This only occurs when the LIN hardware is in Slave mode.

In Master mode, when no deviating values are specified by the database or CAPL functions, the LIN hardware assumes the frame length derived from the frame identifier.

The keyword `this` and the selectors can be used to access the data of the event that has just been received.

## Selectors

- [linDlcInfo](../Selectors/CAPLfunctionLINDLCInfo.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
