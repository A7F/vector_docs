# frEnableGateway

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long frEnableGateway(long channelA, long channelB);
```

## Description

Activates the gateway. Settings from the [Network-Hardware-Configuration](../../../CANoeCANalyzer/Ribbon/Hardware/NetworkHardware.md) dialog will be overwritten with this function.

## Parameters

- **channelA**: Channel 1 of the gateway
- **channelB**: Channel 2 of the gateway

## Return Values

- **0**: Error

## Example

—

[FlexRay Gateway Mode](../../../CANoeCANalyzer/FlexRay/FlexRayGatewayMode.md)
