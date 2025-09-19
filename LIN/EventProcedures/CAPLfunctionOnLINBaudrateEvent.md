[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/EventProcedures/CAPLfunctionOnLINBaudrateEvent.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » on linBaudrateEvent

# on linBaudrateEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Description

The event procedure `on linBaudrateEvent` is called when the LIN hardware has successfully measured the baudrate of an external master or if the baudrate deviates by more than 0.5% from the last reported value. This only occurs if an external master is being used (in which case the LIN hardware is running in Slave mode).

The keyword `this` and the selectors can be used to access the data of the event that has just been received.

## Selectors

- [linBaudrateEvent](../Selectors/CAPLfunctionLINBaudrateEvent.md)

## Example

—

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
