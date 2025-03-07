[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionMkExtID.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » mkExtId

# mkExtId

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword mkExtId(dword id);
```

## Description

Returns an extended id.

## Parameters

- **id**: Id part of a message.

## Return Values

[Extended identifier](../../../CANoeCANalyzer/General/CANExtendedIdentifier.md)

## Example

```plaintext
...
msg.id = mkExtId(this.id);
...
```

•  Technical References are only available in English

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)