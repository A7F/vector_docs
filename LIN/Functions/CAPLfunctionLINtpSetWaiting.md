[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINtpSetWaiting.md)

**CAPL Functions** » **LIN** » **LINtp_SetWaiting**

# LINtp_SetWaiting

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void LINtp_SetWaiting(long isWaiting);
```

## Description

Sets ISO TP waiting state for the node. When waiting has been activated the node will send FlowControl.Wait frames instead of ConsecutiveFrames, if sending of FlowControl frames has been activated.

## Parameters

- **isWaiting**
  - `0`: Deactivate waiting
  - `1`: Activate waiting
  - `other`: reserved

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
