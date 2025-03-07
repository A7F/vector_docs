[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanGetStdRemoteCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » canGetStdRemoteCount

# canGetStdRemoteCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetStdRemoteCount(long channel);
```

## Description

Gets the total count of standard remote frames of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of standard remote frames, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Count of remote frames on CAN2: %i", canGetStdRemoteCount(2));
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)