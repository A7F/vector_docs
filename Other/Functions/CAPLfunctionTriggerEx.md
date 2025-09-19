[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionTriggerEx.md)

# triggerEx

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » triggerEx

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void triggerEx(char name[]);
```

## Description

Sends a trigger event to a CANoe DE product Logging or Trigger Block specified by **name**.

For a Logging Block, the trigger event starts and stops logging, depending on

- the **trigger mode** (single or toggle trigger)
- the **trigger conditions** for **toggle on** and **toggle off**

set in the [Trigger Configuration](../../../CANoeCANalyzer/FunctionBlocks/Trigger/TriggerConfiguration.md) dialog of this block.

For a Trigger Block, the trigger event starts and stops the data stream (like a filter) for the whole analysis branch or a single analysis window, depending also on **trigger mode** and **trigger conditions** in the **Trigger Configuration** dialog.

If you enter no name, the event will be sent to all Trigger and Logging Blocks that are located behind the CAPL node with the CAPL function `triggerEx()` in the Measurement Setup. If you want the CAPL node to have effect on all Trigger Blocks, the CAPL node has to be placed directly after the online/offline switch.

**Note:** Please note help of the [Trigger Condition: CAPL](../../../CANoeCANalyzer/FunctionBlocks/Trigger/TriggerConditionCAPL.md)

## Parameters

- **name**: Name of the Logging or Trigger Block.

  **Note:** If you use the function in standalone mode and if you activated logging and Trigger Block in the standalone mode configuration settings you can address the (single) Trigger Block available in this case by passing an empty string as parameter.

## Return Values

—

## Example

```plaintext
on message 100 
{
  write("logging starts in Logging Block ""Logging""");
  triggerEx("Logging"); // start logging
  setTimer(logging,1000); // for 1000 ms
}

on timer logging
{
  triggerEx("Logging"); // Stop logging
}
```

[trigger](CAPLfunctionTrigger.md) • [stop](CAPLfunctionStop.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
