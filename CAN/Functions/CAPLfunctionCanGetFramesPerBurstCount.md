[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanGetFramesPerBurstCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » canGetFramesPerBurstCount

# canGetFramesPerBurstCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetFramesPerBurstCount(long channel, ValueSelector selector);
```

## Description

Gets the count of frames per burst of a CAN channel. The kind of value to be returned (average, current, maximum or minimum) can be selected.

## Parameters

- **channel**: CAN channel (1…32).
- **selector**: Value selector:
  - eCurrValue = current
  - eMinValue = minimum
  - eMaxValue = maximum
  - eAvgValue = average

## Return Values

Count of frames per burst, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Average frames per burst on CAN1: %i", canGetFramesPerBurstCount(1, eAvgValue));
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)