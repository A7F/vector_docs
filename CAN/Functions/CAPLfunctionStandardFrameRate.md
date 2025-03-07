[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionStandardFrameRate.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » StandardFrameRate

# StandardFrameRate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long StandardFrameRate ()
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
CANx.StandardFrameRate
```

## Description

Returns the current rate of standard CAN messages on channel **x**.

Valid **x** values: 1…32

## Parameters

—

## Return Values

Current rate of standard CAN frames on channel **x** in messages per second.

## Example

```
write ("Rate of standard frames on CAN1 = %d", CAN1.StandardFrameRate);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)