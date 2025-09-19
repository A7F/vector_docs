[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTNodeAdr.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostNodeAdr

# OnMostNodeAdr

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
OnMostNodeAdr(long nodeadr);
```

## Description

The node address of the network interface to the MOST bus has changed. The value of the new node address is in the **nodeadr** parameter.

Within this event procedure the functions [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md) and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

CAPL nodes are transparent to the controller events. Please use the Multibus Filter or MOST Filter, to filter these events in nodal sequences.

## Parameters

- **nodeadr**: New value of the node address.

## Return Values

—

## Example

—

[mostGetNodeAdr](../Functions/CAPLfunctionMOSTGetNodeAdr.md) • [mostSetNodeAdr](../Functions/CAPLfunctionMOSTSetNodeAdr.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
