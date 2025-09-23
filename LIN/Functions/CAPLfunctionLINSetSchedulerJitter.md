[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetSchedulerJitter.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linSetSchedulerJitter

# linSetSchedulerJitter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long linSetSchedulerJitter (long mode); // form 1`
- `long linSetSchedulerJitter (long mode, long jitterInMicSecs); // form 2`

## Description

Sets/resets the jitter mode and the jitter of the LIN hardware scheduler. (the channel is determined by the CAPL program context).

**Note**: If the Master node is not simulated or no schedule tables are defined, then this function will have no effect.

## Parameters

- **mode**
  - `0`: deactivates the jitter;
  - `1`: sets the min-/max-mode; the minimum (0) and the maximum (specified value) jitter will be used alternatively
  - `2`: sets the random jitter-mode; the jitter-offset will be equally distributed in the min/max range

- **jitterInMicSecs**
  - The jitter in microseconds to be used.
  - Default: Jitter value from LDF.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```c
on key 'j'
{
    if (0 != linSetSchedulerJitter(1))
    {
        // for the next LIN hardware scheduler will use jitter specified in the LDF
    }
}
```
