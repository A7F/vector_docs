[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMostShutdownReason.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostShutdownReason

# OnMostShutdownReason

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

`OnMostShutdownReason(long oldReason, long newReason);`

## Description

This event procedure is called each time when the shutdown reason changes.

Within this event procedure the functions [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md) and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

The following reason values are defined based on the MOST Specification 3.0:

- **0**: No result available
- **1**: No fault saved
- **2**: Failure ‘Sudden Signal Off’
- **3**: Failure ‘Critical Unlock’

## Parameters

- **oldReason**: The reason value for the second last shutdown.
- **newReason**: The reason value for the last shutdown.

## Return Values

—

## Example

—

[mostGetShutdownReason](../Functions/CAPLfunctionMOSTGetShutdownReason.md) • [mostSetShutdownReason](../Functions/CAPLfunctionMOSTSetShutdownReason.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
