[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTMPRDelayed.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostMPRDelayed

# OnMostMPRDelayed

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
OnMostMPRDelayed(long mpr);
```

## Description

The value of the maximum position register in the MOST chip has not changed since the last network change event (NCE) for t_MPRDelayed (see MOST Spec 2V3 – 3.9 Timing Definitions). The **mpr** parameter indicates the value of the maximum position register.

Within this event procedure, the functions [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md), and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

CAPL nodes are transparent to the controller events. Please use the Multibus Filter or MOST Filter, to filter these events in nodal sequences.

## Parameters

- **mpr**: Value of the Maximum Position Register in the MOST chip.

## Return Values

—

## Example

—

[OnMostMPR](CAPLfunctionOnMOSTMPR.md) • [mostGetNceType](../Functions/CAPLfunctionMOSTGetNCEType.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)