[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTMPR.md)

**CAPL Functions** » **MOST** » **OnMostMPR**

# OnMostMPR

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
OnMostMPR(long value);
```

## Description

A change is made to the Maximum Position Register of the MOST chip, i.e. the number of devices in the MOST ring. The **value** parameter contains the new value of the Maximum Position Register.

Within this event procedure, the functions [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md), and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

CAPL nodes are transparent to the controller events. Please use the Multibus Filter or MOST Filter to filter these events in nodal sequences.

## Parameters

- **value**: New value of the Maximum Position Register of the MOST chip.

## Return Values

—

## Example

—

[mostGetMPR](../Functions/CAPLfunctionMOSTGetMPR.md)
