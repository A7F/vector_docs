[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionExtendedFrameRate.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » ExtendedFrameRate

# ExtendedFrameRate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long ExtendedFrameRate ()
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
CANx.ExtendedFrameRate
```

## Description

Returns the current rate of extended CAN messages on channel **x**.

Valid **x** values: 1…32

## Parameters

—

## Return Values

Current rate of extended CAN messages on channel **x** in messages per second.

## Example

```plaintext
write ("Rate of extended frames on CAN1 = %d", CAN1.ExtendedFrameRate);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)