[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CarMaker/Functions/CAPLfunctionCarMakerSubscribe.md)

[CAPL Functions](../../CAPLfunctions.md) » [CarMaker Interface](../CAPLfunctionsCarMakerOverview.md) » CarMaker_Subscribe

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)