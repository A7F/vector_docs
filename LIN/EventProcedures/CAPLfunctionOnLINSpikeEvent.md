[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/EventProcedures/CAPLfunctionOnLINSpikeEvent.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » on linSpikeEvent

# on linSpikeEvent

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Description

The event procedure `on linSpikeEvent` is called when the LIN hardware detects a spike on the bus (i.e. a short dominant signal that is too short to be a valid wake-up frame or to be accepted as a start bit and be reported by the UART).

The keyword `this` and the selectors can be used to access the data of the event that has just been received.

## Selectors

- [linSpikeEvent](../Selectors/CAPLfunctionLINSpikeEvent.md)

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
