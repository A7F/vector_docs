[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTSBC.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostSBC

# OnMostSBC

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

`OnMostSBC(long value);`

## Description

A change is made to the Synchronous Bandwidth Register of the MOST chips, i.e. the distribution into synchronous/asynchronous transmission bandwidth. The 'value' parameter contains the new value of the Synchronous Bandwidth Register (see also Datasheet for the OS8104).

Within this event procedure the functions [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md) and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

CAPL nodes are transparent to the controller events. Please use the Multibus Filter or MOST Filter, to filter these events in nodal sequences.

## Parameters

- **value**: New value of Synchronous Bandwidth Register of the MOST chip.

## Return Values

—

## Example

—

[mostGetSBC](../Functions/CAPLfunctionMOSTGetSBC.md) • [mostSetSBC](../Functions/CAPLfunctionMOSTSetSBC.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
