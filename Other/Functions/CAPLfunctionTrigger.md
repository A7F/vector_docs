[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionTrigger.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » trigger

# trigger

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void trigger();
```

## Description

Sends a trigger event to all CANoe DE product Logging or Trigger Blocks.

For a Logging Block, the trigger event starts and stops logging, depending on:

- the **trigger mode** (single or toggle trigger)
- the **trigger conditions** for **toggle on** and **toggle off**

set in the [Trigger Configuration](../../../CANoeCANalyzer/FunctionBlocks/Trigger/TriggerConfiguration.md) dialog of this block.

For a trigger block, the trigger event starts and stops the data stream (like a filter) for the whole analysis branch or a single analysis window, depending also on **trigger mode** and **trigger conditions** in the **Trigger Configuration** dialog.

**Note**: Please note help of the [Trigger Condition: CAPL](../../../CANoeCANalyzer/FunctionBlocks/Trigger/TriggerConditionCAPL.md).

## Parameters

—

## Return Values

—

## Example

```plaintext
on message 100 
{
  write("logging start");
  trigger(); // start logging
  setTimer(logging,1000); // for 1000 ms
}

on timer logging
{
  trigger(); // Stop logging
}
```

[triggerEx](CAPLfunctionTriggerEx.md) • [stop](CAPLfunctionStop.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)