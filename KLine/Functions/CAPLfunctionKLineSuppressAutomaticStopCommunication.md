[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineSuppressAutomaticStopCommunication.md)

**CAPL Functions** » [K-Line](../CAPLfunctionsKLineOverview.md) » KLine_SuppressAutomaticStopCommunication

# KLine_SuppressAutomaticStopCommunication

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long KLine_SuppressAutomaticStopCommunication(long doSuppress)
```

## Description

For a fast init ECU, automatic sending of a Stop communication command will be suppressed after closing the channel or a S3 timeout.

## Parameters

- **doSuppress**  
  1: Suppress sending of stop communication command  
  0: do not suppress sending of stop communication command

## Return Values

On success 0, otherwise a value less than 0.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
