# canResetStatistics

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void canResetStatistics();
void canResetStatistics(long channel);
```

## Description

Resets CAN channel statistics.

**Note**

There are two ways to call this function:

- Calling this function **without the explicit channel** is only possible from a CAPL program defined in the Simulation/Test Setup. The statistics for the channel determined by the current [bus context](../../Other/Functions/CAPLfunctionGetBusContext.md) are reset.
- The function **with the explicit channel** can be called from a CAPL program defined in Measurement Setup only.

## Parameters

- **channel**: CAN channel (1-based)

## Return Values

—

## Example

```plaintext
on key 'r' 
{ 
   // reset statistics on CAN 1
   canResetStatistics(1);
}
```
