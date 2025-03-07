[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionTxChipErrorCount.md)

**CAPL Functions** » **CAN** » **TxChipErrorCount**

# TxChipErrorCount

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TxChipErrorCount ()
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
CANx.TxChipErrorCount
```

## Description

Returns the current number of Tx errors in the CAN receiver of channel **x**.

Valid **x** values: 1…32

## Parameters

—

## Return Values

Current number of errors in the CAN receiver of channel **x**.

## Example

```plaintext
write ("Number of Tx errors in receiver of CAN1 = %d", CAN1.TxChipErrorCount);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)