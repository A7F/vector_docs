[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanGetExtDataCount.md)

**CAPL Functions** » [CAN](../CAPLfunctionsCANOverview.md) » canGetExtDataCount

# canGetExtDataCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetExtDataCount(long channel);
```

## Description

Gets the total count of extended data frames of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of extended data frames, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Total count of extended data frames on CAN1: %i", canGetExtDataCount(1));
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)