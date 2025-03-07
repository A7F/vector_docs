[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/A429/EventProcedures/CAPLfunctionA429OnA429Error.md)

# on a429error

[CAPL Functions](../../CAPLfunctions.md) » [A429](../CAPLfunctionsA429Overview.md) » on a429error

**Valid for**: CANoe DE • CANoe4SW DE

## Description

The event procedure **on a429error** is called on every event related to a general ARINC error (e.g. if a hardware queue overflow or a transmission error occurs). The error type is available in the **error** selector.

ARINC errors are also monitored with **statistics system variables**.

## Selectors

- -

## Example

```
on a429error
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)