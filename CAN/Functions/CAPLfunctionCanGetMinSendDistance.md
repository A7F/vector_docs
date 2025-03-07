[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanGetMinSendDistance.md)

**CAPL Functions** » **CAN** » **canGetMinSendDistance**

# canGetMinSendDistance

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetMinSendDistance(long channel);
```

## Description

Gets the minimum distance between two consecutive frames of a CAN channel in milliseconds.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Minimum distance between two consecutive frames in milliseconds, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Minimum send distance on CAN1: %i [ms]", canGetMinSendDistance(1));
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)