# CarMaker_Subscribe

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CarMaker_Subscribe(char group[], double freq_hz);
```

## Description

Subscribes a group of CarMaker quantities as CANoe system variables. The CANoe system variables are defined in the CarMaker system variable namespace. Each call to this function automatically unsubscribes any previous subscription.

## Parameters

- **group**: Name of the group of quantities to subscribe.
- **freq_hz**: The frequency at which the values are to be sent. The reception is then processed inside the polling function.

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
// subscribe to quantities of CarMaker
gErrorState = CarMaker_Subscribe("TC1_Group", gFreq_Hz);
```
