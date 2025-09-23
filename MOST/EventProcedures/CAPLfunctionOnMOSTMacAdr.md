[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTMacAdr.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostMacAdr

# OnMostMacAdr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
OnMostMacAdr(int64 macAdr);
```

## Description

The MAC address (48 bit) of the network interface to the MOST bus has changed.

Within this event procedure the functions [mostEventChannel, mostEventTime and mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

CAPL nodes are transparent to the controller events. Please use the MOST Application Filter, to filter these events in nodal sequences.

## Parameters

- **macAdr**: New value of the MAC address.

## Return Values

—

## Example

—

[mostSetMacAdr](../Functions/CAPLfunctionMOSTSetGetMacAdr.md) • [outputMostEthPkt](../Functions/CAPLfunctionMOSTOutputMostEthPkt.md)
