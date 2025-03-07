[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetInterruptingHeaderTransmits.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetInterruptingHeaderTransmits

# linSetInterruptingHeaderTransmits

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long linSetInterruptingHeaderTransmits (long enable);
```

## Description

By calling this function, the channel specified by the current bus context will be switched to interrupting mode.

In default mode, requests to transmit headers will be queued until a network idle condition occurs. This means that the networks level has to be recessive for a short period of time. Headers will only start to be transmitted on the network after this condition is met.

Calling `linSetInterruptingHeaderTransmits(1)` disables the network idle verification. Headers transmitted by CAPL function calls, or by other means in CANoe, will now be transmitted immediately. This will interrupt ongoing transmissions of slave responses if a collision occurs.

This option will affect all headers sent by the LIN hardware.

This function can only be called in CAPL on prestart handlers.

## Parameters

- **enable**  
  This parameter specifies whether interrupting headers mode on the LIN channel will be enabled or disabled.
  - 0: Disable
  - 1: Enable

## Return Values

—

## Example

```plaintext
on prestart {
    linSetInterruptingHeaderTransmits (1);
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)