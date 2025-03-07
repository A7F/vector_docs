[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILResetBlockedTxTpCts.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_ResetBlockedTxTpCts**

# Iso11783IL_ResetBlockedTxTpCts

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_ResetBlockedTxTpCts(); //Form 1
long Iso11783IL_ResetBlockedTxTpCts(dbNode node); //Form 2
```

## Description

Resets all CTS messages that were blocked with [Iso11783IL_BlockTxTpCts](CAPLfunctionIso11783ILBlockTxTpCts.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = Iso11783IL_BlockTxTpCts(1); // Block the first CTS message
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
// Reset blocked TP.CTS messages by pressing ‘a’ on the keyboard.
on key 'a' {
  long res;
  res = Iso11783IL_ResetBlockedTxTpCts(); // Resets all blocked TP.CTS messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)