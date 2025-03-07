[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanGetStdRemoteRate.md)

**CAPL Functions** » **CAN** » **canGetStdRemoteRate**

# canGetStdRemoteRate

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetStdRemoteRate(long channel, ValueSelector selector);
```

## Description

Gets the rate of standard remote frames of a CAN channel in frames per second [fr/s]. The kind of value to be returned (average, current, maximum or minimum) can be selected.

## Parameters

- **channel**: CAN channel (1…32).
- **selector**: Value selector:
  - eCurrValue = current
  - eMinValue = minimum
  - eMaxValue = maximum
  - eAvgValue = average

## Return Values

Rate of standard remote frames in frames per second, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Remote frames on CAN2: %i [fr/s]", canGetStdRemoteRate(2, eCurrValue));
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)