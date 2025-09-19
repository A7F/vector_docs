[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINtpFCPreTransmit.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » LINtp_FCPreTransmit

# LINtp_FCPreTransmit

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void LINtp_FCPreTransmit(byte fcData[]);
```

## Description

When the usage of FlowControl frames has been activated with [LINtp_ActivateFCTransmission](CAPLfunctionLINtpActivateFCTransmission.md), each FlowControl frame is forwarded to this callback function before it is sent.

## Parameters

- **fcData**: Data of the FC frame.

## Return Values

—

## Example

```plaintext
void LINtp_FCPreTransmit (byte fcData[])
{
  write( "FlowControl to be sent: %02x %02x %02x %02x (%d byte)"
  , fcData[0] , fcData[1] , fcData[2] , fcData[3], elcount(fcData));
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
