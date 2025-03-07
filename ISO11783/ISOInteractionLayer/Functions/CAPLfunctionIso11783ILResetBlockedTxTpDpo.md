[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILResetBlockedTxTpDpo.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_ResetBlockedTxTpDpo

# Iso11783IL_ResetBlockedTxTpDpo

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_ResetBlockedTxTpDpo();` //Form 1
- `long Iso11783IL_ResetBlockedTxTpDpo(dbNode node);` //Form 2

## Description

Resets all DPO messages that were blocked with [ISO11783IL_BlockTxTpDpo](CAPLfunctionIso11783ILBlockTxTpDpo.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = ISO11783IL_BlockTxTpDpo(1); // Block the first ETP.DPO message
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
// Reset blocked ETP.DPO messages by pressing ‘a’ on the keyboard.
on key 'a'{
  long res;
  res = ISO11783IL_ResetBlockedTxTpDpo(); // Resets all blocked ETP.DPO messages.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)