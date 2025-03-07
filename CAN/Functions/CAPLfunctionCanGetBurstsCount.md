[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanGetBurstsCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » canGetBurstsCount

# canGetBurstsCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long canGetBurstsCount(long channel);
```

## Description

Gets the total count of bursts of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of bursts, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
long value;

value = canGetBurstsCount(1);
// Do something with the value, e.g.:
if (value > 100) {
  // Some action…
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)