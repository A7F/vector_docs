[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINtpActivateFCTransmission.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » LINtp_ActivateFCTransmission

# LINtp_ActivateFCTransmission

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void LINtp_ActivateFCTransmission(long blockSize);
```

## Description

Activate the usage of FlowControl frames. These frames will be indicated in the optional callback [LINtp_FCPreTransmit](CAPLfunctionLINtpFCPreTransmit.md) before sending.

## Parameters

- **blockSize**
  - `<0`: Stops sending FlowControl frames
  - `[0, 255]`: Sends FlowControl frames with this block size
  - Other: reserved

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)