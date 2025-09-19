# output (AFDX)

[CAPL Functions](../../CAPLfunctions.md) » [AFDX »](../CAPLfunctionsAFDXOverview.md) output AFDX

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

- `void output (a664Message aMessage) (1)`
- `void output (a664Frame aFrame) (2)`

## Description

This function outputs the object from the program block of the analysis branch. Use `output` inside the appropriate event procedure in order to forward the event to the next block in the analysis branch. If the function is not called, then the event is not forwarded. Thus, events will be filtered by the CAPL program when omitting this function.

The function must not be used in the **Simulation Setup** branch. For transmitting an object of type `a664Frame` or `a664Message` use the functions [A664TriggerFrame](CAPLfunctionA664TriggerFrame.md) and [A664TriggerMessage](CAPLfunctionA664TriggerMessage.md).

## Parameters

—

## Return Values

—

## Example

```plaintext
on a664Message * {
  #if MEASUREMENT_SETUP
  output(this);
  #endif
}

// or on frame level

on a664Frame * {
  #if MEASUREMENT_SETUP
  output(this);
  #endif
}
```
