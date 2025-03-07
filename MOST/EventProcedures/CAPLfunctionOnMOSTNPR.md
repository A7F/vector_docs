[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTNPR.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostNPR

# OnMostNPR

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
OnMostNPR(long npr);
```

## Description

The Node Position Register of the MOST chip, i.e. the position of the device in the MOST ring, has changed. The parameter **value** contains the new value of the Node Position Register.

Within this event procedure the functions [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md) and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

CAPL nodes are transparent to the controller events. Please use the Multibus Filter or MOST Filter, to filter these events in nodal sequences.

## Parameters

- **npr**: New value of the Node Position Register in the MOST chip.

## Return Values

—

## Example

—

[mostGetNPR](../Functions/CAPLfunctionMOSTGetNPR.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)