[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanGetRxErrorCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » canGetRxErrorCount

# canGetRxErrorCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long canGetRxErrorCount(long channel);
```

## Description

Gets the total count of receive errors of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of receive errors, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Receive errors on CAN1: %i", canGetRxErrorCount(1));
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)