[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanGetOverloadFrameCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » canGetOverloadFrameCount

# canGetOverloadFrameCount

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long canGetOverloadFrameCount(long channel);
```

## Description

Gets the total count of overload frames of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of overload frames, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Overload frame count of CAN1: %i", canGetOverloadFrameCount(1));
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)