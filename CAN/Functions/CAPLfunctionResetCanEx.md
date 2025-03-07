[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionResetCanEx.md)

**CAPL Functions** » **CAN** » **ResetCanEx**

# ResetCanEx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
void ResetCanEx(long channel);
```

## Description

Resets the CAN controller for one specific CAN channel. Can be used to reset the CAN controller after a BUSOFF or to activate configuration changes. Since execution of the function takes a certain amount of time and the CAN controller is disconnected from the bus for a brief period messages may be lost.

**Note:** The Rx queue of the CAN channel will not be flushed by default.

## Parameters

- **channel**: CAN channel

## Return Values

—

## Example

```c
on key 'r' { // After BUSOFF the controller on Channel 2 is reset
    resetCanEx(2);
}
```

[resetCan](CAPLfunctionResetCan.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)