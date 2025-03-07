[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressSetContinuousDisturbanceWhiletrigger.md)

# CANstressSetContinuousDisturbanceWhileTrigger

[CAPL Functions](../../CAPLfunctions.md) » [CANstresss](../CAPLfunctionsCANstressOverview.md) » CANstressSetContinuousDisturbanceWhileTrigger

**Valid for**: CANoe DE

## Function Syntax

```plaintext
void CANstressSetContinuousDisturbanceWhileTrigger (dword type);
```

## Description

Sets the **Continuous disturbance (while trigger)** mode. The continuous disturbance will prevail for as long as the trigger is active. Please note that this mode is generally only useful in conjunction with a software trigger.

## Parameters

- **type**: Defines the type of continuous disturbance. The disturbance can be associated with dominant or recessive bits or it can be an analog disturbance. 2 indicates a dominant disturbance, 3 a recessive disturbance and 4 an analog disturbance (only in conjunction with CANstress DR).

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)