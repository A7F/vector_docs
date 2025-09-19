[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTAllocTable.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostAllocTable

# OnMostAllocTable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
OnMostAllocTable();
```

## Description

`OnMostAllocTable` is called as soon as the network interface detects a change in the MOST allocation table. The allocation table contains the reservation status of the synchronous MOST channels.

Supplemental information can be called up within this procedure by the [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md) and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) functions.

Controller events are passed through CAPL nodes. Please use the Multibus Filter or MOST Filter to filter these events in node chains.

## Parameters

—

## Return Values

—

## Example

—

• [mostGetAllocTable](../Functions/CAPLfunctionMOSTGetAllocTable.md) • [mostAllocTableGetCL](../Functions/CAPLfunctionMOSTAllocTableGetCL.md) • [mostAllocTableGetSize](../Functions/CAPLfunctionMOSTAllocTableGetSize.md) • [mostAllocTableGetWidth](../Functions/CAPLfunctionMOSTAllocTableGetWidth.md) •

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
