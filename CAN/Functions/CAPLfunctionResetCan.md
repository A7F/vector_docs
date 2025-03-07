[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionResetCan.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » resetCan

# resetCan

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
void resetCan();
```

## Description

Resets the CAN controller. Can be used to reset the CAN controller after a BUSOFF or to activate configuration changes. Since execution of the function takes some time and the CAN controller is disconnected from the bus briefly, messages can be lost when this is performed.

**Note**  
With this function you can reset CAN1 and CAN2. If only one specific CAN channel is used, `resetCan` stops with an error and the CAN channels keep offline. In this case the [ResetCanEx](CAPLfunctionResetCanEx.md) function has to be used. The function [resetCanEx](CAPLfunctionResetCanEx.md) can be used for all channels.

## Parameters

—

## Return Values

—

## Example

```plaintext
on key 'r' { // Controller is reset after BUSOFF
    resetCan();
}
```

[setOcr](CAPLfunctionSetOcr.md) • [setBtr](CAPLfunctionSetBtr.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)