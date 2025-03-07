[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILResetBlockedTxTpCts.md)

**CAPL Functions » ISO11783 » File Server Interaction Layer (FS IL) » FSIL_ResetBlockedTxTpCts**

# FSIL_ResetBlockedTxTpCts

[Valid for: CANoe DE • CANoe4SW DE](../../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long FSIL_ResetBlockedTxTpCts( ); //Form 1
long FSIL_ResetBlockedTxTpCts( dbNode node); //Form 2
```

## Description

Resets all CTS messages that were blocked with [FSIL_BlockTxTpCts](CAPLfunctionIso11783FSILBlockTxTpCts.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = FSIL_BlockTxTpCts(1); // Block the first CTS message
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
// Reset blocked TP.CTS messages by pressing ‘a’ on the keyboard.
on key 'a' {
  long res;
  res = FSIL_ResetBlockedTxTpCts(); // Resets all blocked TP.CTS messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)