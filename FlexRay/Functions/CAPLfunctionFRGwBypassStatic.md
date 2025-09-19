[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRGwBypassStatic.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frGwBypassStatic

# frGwBypassStatic

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The bypass should be deactivated within the [on frPDU](../EventProcedures/CAPLfunctionOnFRPDU.md) or [on frFrame](../EventProcedures/CAPLfunctionOnFRFrame.md) handler of the affected object (PDU, frame). The time to the next transmission is deterministic here. See example 2 below.

## Function Syntax

```plaintext
long frGwBypassStatic (long bypass, long channel, long slotId, long baseCycle, long cycleRepetition); // form 1
long frGwBypassStatic (long bypass, long channel, long slotId, long baseCycle, long cycleRepetition, long channelMask); // form 2
```

## Description

Activates/deactivates the automatic routing for the given slot. The function can be used during measurement.

Form 2 can only be used FlexRay with dual channel gateway (AB-AB-Gateway) mode, see [FlexRay gateway](../../../CANoeCANalyzer/FlexRay/FlexRayGatewayMode.md#TwoChannelGateway).

## Parameters

- **bypass**  
  0 = Routing deactivated  
  1 = Routing activated

- **channel**  
  Output channel of the gateway.

- **Slotid**  
  Slot number

- **baseCycle**  
  Base cycle

- **cycleRepetition**  
  Repetition factor

- **channelMask**  
  Channel mask  
  Values:
  - 1: Channel A
  - 2: Channel B
  - 3: Channel A+B

## Return Values

- **0**  
  Error

- **1**  
  OK

## Example

—

[FlexRay Gateway Mode](../../../CANoeCANalyzer/FlexRay/FlexRayGatewayMode.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
