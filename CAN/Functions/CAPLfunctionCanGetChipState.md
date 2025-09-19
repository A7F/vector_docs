# canGetChipState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long canGetChipState(long channel);
```

## Description

Gets the current chip state of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Chip state of a CAN channel. Returned values are:

- **0**: Value not available
- **1**: Simulated
- **2**: Not used
- **3**: Error Active
- **4**: Warning Level
- **5**: Error Passive
- **6**: Bus Off

You may find further information about the chip states also on the [Bus Statistics Window](../../../CANoeCANalyzer/Windows/BusStatistic/BusStatisticWindowCAN.md) page.

## Example

```plaintext
long value = canGetChipState(1);
// Now do something with the value:
switch (value) {
  case 1:
    write("Simulated");
    break;
  case 3:
    write("Error Active");
    break;
  case 4:
    write("Warning Level");
    break;
  case 5:
    write("Error Passive");
    break;
  default:
    break;
}
```
