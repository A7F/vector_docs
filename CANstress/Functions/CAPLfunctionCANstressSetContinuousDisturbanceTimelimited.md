[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressSetContinuousDisturbanceTimelimited.md)

**CAPL Functions** » **CANstresss** » **CANstressSetContinuousDisturbanceTimeLimited**

# CANstressSetContinuousDisturbanceTimeLimited

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
void CANstressSetContinuousDisturbanceTimeLimited (dword duration, dword type);
```

## Description

Sets the **Continuous disturbance (time limited)** mode. If the disturbance has not previously been terminated by means of an explicit command such as [CANstressStop](CAPLfunctionCANstressStop.md), the end of the test module or the end of the measurement, it will prevail for the period of time set in **duration**.

## Parameters

- **time**: Defines the maximum length of the continuous disturbance. The length is specified in ms and must be greater than 0.
- **type**: Defines the type of continuous disturbance. The disturbance can be associated with dominant or recessive bits or it can be an analog disturbance. 2 indicates a dominant disturbance, 3 a recessive disturbance and 4 an analog disturbance (only in conjunction with **CANstress** DR).

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)