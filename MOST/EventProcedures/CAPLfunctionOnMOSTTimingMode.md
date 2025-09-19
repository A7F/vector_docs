[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTTimingMode.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostTimingMode

# OnMostTimingMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
OnMostTimingMode(long mode);
```

## Description

The `OnMostTimingMode()` event procedure is called if the timing mode of the MOST hardware has been changed.

Supplemental information can be called up within this procedure by the [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md) and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) functions.

Controller events are passed through CAPL nodes. Please use the Multibus Filter or MOST Filter to filter these events in node chains.

## Parameters

- **mode**:
  - `0`: Timing Slave
  - `1`: Timing Master

## Return Values

—

## Example

—

[mostSetTimingMode](../Functions/CAPLfunctionMOSTSetTimingMode.md) • [mostGetTimingMode](../Functions/CAPLfunctionMOSTGetTimingMode.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
