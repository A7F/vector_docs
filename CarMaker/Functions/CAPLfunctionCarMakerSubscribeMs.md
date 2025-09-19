# CarMaker_SubscribeMs

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CarMaker_SubscribeMs(char group[], double interval_ms);
```

## Description

Subscribes a group of CarMaker quantities as CANoe system variables. The CANoe system variables are defined in the CarMaker system variable namespace. Each call to this function automatically unsubscribes any previous subscription. This function is identical to [CarMaker_Subscribe](CAPLfunctionCarMakerSubscribe.md) with the difference that the second parameter is specified as an interval instead of a frequency.

## Parameters

- **group**: Name of the group of quantities to subscribe.
- **interval_ms**: The interval between successive transmissions of values for the subscribed quantities. The reception is then processed inside the polling function.

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
// subscribe to quantities of CarMaker
gErrorState = CarMaker_Subscribe("TC1_Group", gFreq_Hz);
```
