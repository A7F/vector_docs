[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionRxChipErrorCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » RxChipErrorCount

# RxChipErrorCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long RxChipErrorCount ()
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
CANx.RxChipErrorCount
```

## Description

Returns the current Rx error count in the receiver of channel **x**.

Valid **x** values: 1…32

## Parameters

—

## Return Values

Current error count in the receiver of channel **x**.

## Example

```plaintext
write ("Rx error count in the receiver of CAN1 = %d", CAN1.RxChipErrorCount);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)