[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINtpDataCon.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » LINtp_DataCon

# LINtp_DataCon

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void LINtp_DataCon(long count);
```

## Description

This CAPL callback confirms the number of data bytes successfully sent.

## Parameters

- **count**: Number of bytes sent.

## Return Values

—

## Example

```plaintext
void LINtp_DataCon(long count)
{
  write( "sent %d byte", count);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)