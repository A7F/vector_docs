[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressSetContinuousDisturbanceUntilstop.md)

**CAPL Functions** » **CANstresss** » **CANstressSetContinuousDisturbanceUntilStop**

# CANstressSetContinuousDisturbanceUntilStop

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void CANstressSetContinuousDisturbanceUntilStop (dword type);
```

## Description

Sets the **Continuous disturbance (until stop)** mode. Once the trigger has been activated, the continuous disturbance will prevail until the **CANstress** device is deactivated (e.g. by means of the [CANstressStop](CAPLfunctionCANstressStop.md) function) and/or the measurement or test module is terminated.

## Parameters

- **type**: Defines the type of continuous disturbance. The disturbance can be associated with dominant or recessive bits or it can be an analog disturbance. 2 indicates a dominant disturbance, 3 a recessive disturbance and 4 an analog disturbance (only in conjunction with **CANstress** DR).

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)