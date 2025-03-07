[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILResetBlockedTxTpDt.md)

**CAPL Functions** » **J1939** » **J1939 IL** » **J1939ILResetBlockedTxTpDt**

# J1939ILResetBlockedTxTpDt

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `long J1939ILResetBlockedTxTpDt(); //Form 1`
- `long J1939ILResetBlockedTxTpDt(dbNode node); //Form 2`

## Description

Resets all DT messages that were blocked with [J1939ILBlockTxTpDt](CAPLfunctionJ1939ILBlockTxTpDt.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```c
on start {
  long res;
  res = J1939ILBlockTxTpDt(6, 4, 0); // Block 4 packets of the TP.DT message, starting with packet no. 6.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}

on key 'a' {
  long res;
  res = J1939ILResetBlockedTxTpDt(); // Resets blocked TP.DT messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)