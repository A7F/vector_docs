[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTShutdownFlag.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostShutdownFlag

# OnMostShutdownFlag

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
OnMostShutdownFlag(long oldstate, long newstate);
```

## Description

This event procedure is called each time the state of the Shutdown flag changes.

Within this event procedure the functions [mostEventChannel, mostEventTime and mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

## Parameters

- **oldstate**: Old state of the Shutdown Flag.
- **newstate**: New state of the Shutdown Flag.

## Return Values

- **1**: Shutdown Flag set.
- **0**: Shutdown Flag not set.

## Example

—

[mostSetShutDownFlagUsage](../Functions/CAPLfunctionMOSTSetGetShutDownFlagUsage.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
