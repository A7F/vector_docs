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
