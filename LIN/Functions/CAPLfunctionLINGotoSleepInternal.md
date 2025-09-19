[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGotoSleepInternal.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linGotoSleepInternal

# linGotoSleepInternal

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long linGotoSleepInternal();
```

## Description

Sets the LIN hardware to Sleep mode without sending a go-to-sleep-command on the network. Calling this function in the event procedure [on prestart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) leads to measurement start in sleep mode.

## Parameters

—

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```plaintext
// start measurement in Sleep mode
on preStart
{
  linGotoSleepInternal();
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
