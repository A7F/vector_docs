[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetBaudrateDetectionRange.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetBaudrateDetectionRange

# linSetBaudrateDetectionRange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long linSetBaudrateDetectionRange(long rangeInPercent);
```

## Description

With this function, the baudrate detection range can be increased or decreased. The default range is +/- 15%. Note that the detection range will always be symmetrical.

## Parameters

- **rangeInPercent**: The detection range in percent.
  - Value range: 0-30
  - Default: 15

## Return Values

If successful, a value unequal to zero.

## Example

—

[linSetBaudrate](CAPLfunctionLINSetBaudrate.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
