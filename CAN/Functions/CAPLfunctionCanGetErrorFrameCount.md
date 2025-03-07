[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanGetErrorFrameCount.md)

**CAPL Functions** » [CAN](../CAPLfunctionsCANOverview.md) » canGetErrorFrameCount

# canGetErrorFrameCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetErrorFrameCount(long channel);
```

## Description

Gets the total count of error frames of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of error frames, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Total count of error frames on CAN2: %i", canGetErrorFrameCount(2));
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)