[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINtpSetMaximumReceiveLength.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » LINtp_SetMaximumReceiveLength

# LINtp_SetMaximumReceiveLength

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void LINtp_SetMaximumReceiveLength(dword maxRecLen);
```

## Description

Sets maximum number of bytes node can receive. If more data is indicated in a FirstFrame and FlowControl frames have been activated, an **overflow** FlowControl frame is sent.

**Note:** Note that only a maximum of 4095 bytes can be sent using LINtp.

## Parameters

- **maxRcLen**: The maximum number of bytes of segmented data accepted.

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
