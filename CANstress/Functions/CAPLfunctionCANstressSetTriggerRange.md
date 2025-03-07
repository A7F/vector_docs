[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressSetTriggerRange.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANstresss](../CAPLfunctionsCANstressOverview.md) » CANstressSetTriggerRange

# CANstressSetTriggerRange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void CANstressSetTriggerRange (dword fromId, dword toId);
```

## Description

Sets a range for message IDs, which will activate triggers. Both simple and extended CAN message IDs can be specified. However, the corresponding mode must be set in the basic configuration!

## Parameters

- **fromId**: Sets the lower limit of the trigger range.
- **toId**: Sets the upper limit of the trigger range.

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)