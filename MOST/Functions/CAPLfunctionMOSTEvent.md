[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTEvent.md)

# mostEventChannel, mostEventTime, mostEventOrigTime, mostEventTimeNs

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostEventChannel, mostEventTime, mostEventOrigTime, mostEventTimeNs

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following functions can be used within the [event procedures for MOST controller events](../CAPLfunctionsMOSTOverview.md#MOSTControllerEvents) to call up further information on events.

## Function Syntax

- `long mostEventChannel();`
- `dword mostEventTime();`
- `dword mostEventOrigTime();`
- `float mostEventTimeNs();`

## Description

- `long mostEventChannel()` returns the channel over which the event arrived.
- `dword mostEventTime()` returns the time stamp of the event (Units: 10 µs).
- `dword mostEventOrigTime()` returns the hardware-generated time stamp of the event (Units: 10 µs).
- `float mostEventTimeNs()` returns the time stamp of the event (Units: 1 ns).

## Parameters

—

## Return Values

Time stamp

## Example

```c
OnMostNodeAdr(long nodeadr)
{
    write("Node address changed to %04X on channel %d at %fs",
          nodeadr,
          mostEventChannel(),
          mostEventTime() / 100000.0);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
